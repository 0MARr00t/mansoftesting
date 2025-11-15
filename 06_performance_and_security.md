# Performance and Security

## 1) Load Testing (page performance under traffic)

**Goal:** Prove the system meets performance SLAs under expected real-world traffic.

- **Preparation**
    - [ ]  Define SLAs: e.g., *P95 response time ≤ 800ms*, *P99 ≤ 2s*, error rate < 0.5%, throughput target X RPS (requests/sec)*.
    - [ ]  Build realistic user journeys (home, search, product page, add-to-cart, checkout) and weight them by expected traffic distribution.
    - [ ]  Prepare test data/environment that mirrors production (DB size, caches, network latency).
    - [ ]  Instrument monitoring: CPU, memory, disk I/O, DB metrics, app logs, network, APM traces, and error rates.
- **Test execution**
    - [ ]  Ramp-up: slowly increase load from 0 to target RPS over a realistic interval (e.g., 10–30 min).
    - [ ]  Steady-state: hold at target RPS for a soak period (e.g., 30–120 min).
    - [ ]  Measure P50/P90/P95/P99, throughput, error rates, and resource utilization.
    - [ ]  Run tests for peak-user scenarios (e.g., sale event) with higher RPS.
- **Pass criteria**
    - [ ]  Response times meet SLA percentiles.
    - [ ]  Error rate below threshold.
    - [ ]  No resource exhaustion (no OOMs, DB connection pool exhaustion).
    - [ ]  No single-component bottleneck causing cascading failures.
- **Actions on failure**
    - [ ]  Profile and identify hotspots (DB queries, external calls).
    - [ ]  Tune DB indices, cache hot results (Redis), add read replicas, scale app instances, optimize queries.
    - [ ]  Re-run tests after fixes.
- **Tools / notes**
    - Use k6/Locust/JMeter/Gatling; monitor with Prometheus/Grafana, APM (NewRelic/AWS X-Ray). Run from distributed load generators to avoid generator-bound results.

## 2) Stress Testing

**Goal:** Discover breaking points and system behavior under overload and during recovery.

- **Preparation**
    - [ ]  Define targets: increasing concurrency until failures, then observe recovery/resilience.
    - [ ]  Ensure monitoring and alerting active; have a rollback/kill-switch plan.
- **Test execution**
    - [ ]  Ramp beyond expected peak quickly to provoke failures (e.g., 2×, 5× expected peak).
    - [ ]  Identify the point where errors spike or latency explodes.
    - [ ]  Observe behavior under sustained overload (e.g., 10–30 minutes).
    - [ ]  Stop the load and observe system recovery time and data integrity.
- **Expected results**
    - [ ]  System fails gracefully (e.g., queued requests, degraded features, circuit breakers) rather than corrupting data.
    - [ ]  Recovery to healthy state without manual restarts (or with documented manual steps).
    - [ ]  No silent data loss or duplicate transactions.
- **Checks**
    - [ ]  Verify queuing/circuit breakers limit downstream failures.
    - [ ]  Ensure rate-limiting and backpressure are effective.
    - [ ]  Check for partial writes, duplicate orders, or inconsistent DB state.
- **Actions on failure**
    - [ ]  Implement or tune circuit breakers, rate limits, bulkheads.
    - [ ]  Harden scaling policies and autoscaling thresholds.

## 3) Input Validation — SQL Injection (SQLi) & Cross-Site Scripting (XSS)

**Goal:** Prevent all user-supplied input from allowing SQLi or XSS.

### SQL Injection (SQLi)

- **What to test**
    - [ ]  All user input endpoints (forms, parameters, headers, cookies, API endpoints).
    - [ ]  Dynamic query points (search, filters, advanced queries).
- **Test cases**
    - [ ]  Send classic payloads: `' OR '1'='1' --`, `'; DROP TABLE users; --`, `UNION SELECT NULL,NULL--`.
    - [ ]  Blind SQLi patterns (`AND (SELECT ASCII(SUBSTRING((SELECT TOP 1 name FROM users),1,1))) > 64`).
    - [ ]  Test parameter types (numeric vs string) and encoding.
- **Expected results**
    - [ ]  Application never executes injected SQL; input is treated as data, not code.
    - [ ]  Proper error handling — no DB errors or stack traces leaked to user.
- **Mitigations**
    - [ ]  Use parameterized queries / prepared statements / ORMs with parameter binding.
    - [ ]  Input validation and strict typing; least privilege DB user.
    - [ ]  WAF rules as defense-in-depth.
    - [ ]  Database activity monitoring and alerting.

### Cross-Site Scripting (XSS)

- **What to test**
    - [ ]  Any place where user input is rendered in the browser: comments, profile fields, product reviews, search results, error messages.
- **Test cases**
    - [ ]  Stored XSS: submit `<script>alert(1)</script>` in a field and check when rendered by other users.
    - [ ]  Reflected XSS: send URL with `?q=<script>...` and observe reflected output.
    - [ ]  DOM XSS: inject payloads into attributes, event handlers, or JSON contexts.
    - [ ]  Variants: `<img src=x onerror=alert(1)>`, `'"><svg onload=alert(1)>`.
- **Expected results**
    - [ ]  Browser never executes injected scripts.
    - [ ]  Output is HTML-escaped or sanitized per context (HTML, JS, URL, attribute).
- **Mitigations**
    - [ ]  Contextual output encoding/escaping (HTML escape, JS escape, attribute escape).
    - [ ]  Use CSP (Content Security Policy) to block inline scripts.
    - [ ]  Sanitize inputs where rich HTML is allowed, using vetted libraries (DOMPurify for HTML sanitization).
    - [ ]  HttpOnly cookies and proper SameSite flags.

## 4) Password Encryption

**Goal:** Store and handle credentials securely so passwords cannot be recovered if storage is compromised.

- **Storage & hashing**
    - [ ]  Verify passwords are never stored in plaintext.
    - [ ]  Verify a modern, slow password hashing algorithm is used: **Argon2id** (recommended), **bcrypt** or **scrypt** (acceptable), with appropriate cost parameters. (Avoid plain SHA/MD5.)
    - [ ]  Verify unique per-user salt is used (built-in for bcrypt/Argon).
    - [ ]  Verify hashing parameters are periodically reviewed and upgraded as hardware improves.
- **Transmission & handling**
    - [ ]  Verify all password transmission occurs over TLS (HTTPS) only.
    - [ ]  Verify no passwords appear in logs, error messages, or analytics.
    - [ ]  Verify password reset tokens are one-time, short-lived, cryptographically random, and single-use.
- **Password policy**
    - [ ]  Verify enforced complexity or strength policy (or use passphrase guidance) and show clear UX for strength.
    - [ ]  Verify rate-limiting on authentication attempts and account lockout or progressive delays.
    - [ ]  Verify multi-factor authentication (MFA) is available and encouraged/required for high-risk actions.
- **Recovery & rotation**
    - [ ]  Verify password reset flows validate identity securely (not revealing account existence).
    - [ ]  Verify mechanisms for rotating hashing schemes: on next successful login, re-hash with new params.

## 5) Session Management (logout, session expiration)

**Goal:** Sessions should be safe, short-lived, and impossible to hijack or reuse after logout/timeout.

- **Session tokens & cookies**
    - [ ]  Verify session tokens are cryptographically random (sufficient entropy).
    - [ ]  Verify **Secure**, **HttpOnly**, and **SameSite=strict/lax** cookie flags are set appropriately.
    - [ ]  Verify session tokens are stored server-side or use signed JWTs with short expiry and revocation strategy.
    - [ ]  Verify no sensitive state stored client-side in an unencrypted way.
- **Timeouts & logout**
    - [ ]  Verify idle session timeout matches policy and enforces logout.
    - [ ]  Verify explicit logout invalidates server-side session immediately and deletes cookies.
    - [ ]  Verify session invalidation across devices (option to log out from all devices).
- **Token lifecycle & rotation**
    - [ ]  Verify refresh tokens (if used) are stored securely, have limited lifetime, and are revocable.
    - [ ]  Verify token rotation strategy (rotate on use) to reduce replay risk.
- **Session fixation & CSRF**
    - [ ]  Verify session fixation protection (issue new session after login).
    - [ ]  Verify CSRF protection: anti-CSRF tokens for state-changing requests (or SameSite + double-submit when suitable).
    - [ ]  Verify sensitive actions require re-authentication or MFA (e.g., change password, update payment).
- **Multi-tab / concurrency**
    - [ ]  Verify session behavior is consistent across tabs and browsers.
    - [ ]  Verify session timeout triggers in all tabs or forces re-authentication on next action.
- **Logging & monitoring**
    - [ ]  Verify login attempts, successful logins, logouts, and suspicious session activity are logged and alertable.
    - [ ]  Verify unusual session behaviors (multiple IPs, geolocation changes) trigger alerts or step-up auth.

---

## Operational & Testing Best Practices

- [ ]  Always test security changes in staging before prod. For destructive tests (stress, SQLi), use isolated environments and backup data.
- [ ]  Use automated regression suites for performance and security smoke checks after each deployment.
- [ ]  Combine automated scanning (SAST/DAST) with manual penetration testing for high-risk flows.
- [ ]  Maintain an incident playbook for performance outages and a security incident response plan for compromises.
- [ ]  Prioritize fixes by risk: data-loss or compromise > financial loss > availability > UX.