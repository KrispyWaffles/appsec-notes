## Lab 1: Unprotected Admin Functionality

**Vulnerability:** Unprotected admin panel exposed via robots.txt

**How I found it:**
Navigated to /robots.txt on the lab application. The file revealed a
disallowed path: /administrator-panel. Navigated directly to that URL
without any credentials and gained full admin access.

![Lab 1 - Shop Homepage](/appsec-notes/lab1/lab1-shop-homepage.png)

![Lab 1 - robots.txt revealing admin path](/appsec-notes/lab1/lab1-robots-txt.png)

![Lab 1 - Admin panel accessed](/appsec-notes/lab1/lab1-admin-panel.png)

**What I learned:**
robots.txt is meant to guide search engines, not protect pages.
Developers sometimes accidentally expose sensitive paths in it.
Security through obscurity is not access control.

**The Fix:**
Enforce authentication server-side on every sensitive route.
Never rely on hiding a URL as a security measure. Any path that
requires elevated privileges should verify the user's role on
the server before returning a response.

**OWASP Reference:** A01 - Broken Access Control

