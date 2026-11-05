# Web Security Basics Checklist (tester level)

This is a first look that any tester can do. It is **not** a penetration test.

## Authentication and sessions
- [ ] Login rejects wrong, empty and locked credentials with a generic message (no "user not found" vs "wrong password" difference).
- [ ] The password field masks input and the browser does not show it in the address bar.
- [ ] Open the browser tools and look at the session cookie: is it a random, unguessable value (not a readable username or id)?
- [ ] The session cookie has `HttpOnly` and `Secure`, and a sensible `SameSite` and lifetime.
- [ ] **Forge it:** copy the cookie value into a fresh browser, or change the username in it. If the shop opens, authentication is broken.
- [ ] Logout ends the session; the Back button does not show private pages afterwards.
- [ ] Protected pages opened by typing the address without logging in redirect to login.

## Access control
- [ ] Change ids in addresses (`/order?id=1001` to `1002`): you must not see another user's data.
- [ ] A normal user cannot open admin pages by typing their address.
- [ ] Pages that depend on a previous step (confirmation, payment) cannot be opened directly or repeated with the Back button.

## Input handling
- [ ] Script text (`<script>alert(1)</script>`) in fields and addresses is shown as text and never runs.
- [ ] Quote and SQL text (`' OR 1=1 --`) gives a normal error, never a database message.
- [ ] Very long values and unusual characters do not crash the page.

## Transport and headers
- [ ] The site redirects HTTP to HTTPS; no mixed content warnings.
- [ ] Response headers include `Strict-Transport-Security`, `Content-Security-Policy`, `X-Content-Type-Options`, frame protection (`X-Frame-Options` or `frame-ancestors`) and `Referrer-Policy`. (Check with `curl -I https://your-site`.)
- [ ] No server or framework version in headers (`X-Powered-By`, `Server`).

## Errors
- [ ] Error pages are helpful to users and reveal nothing technical (no stack traces, paths, SQL).
- [ ] Unknown addresses show a proper "not found" page.

## Report it well
Give each finding steps, expected and actual result, evidence and the **impact in plain words** ("anyone who knows a username can act as that user").
