
## Lab 2: Unprotected Admin Functionality with Unpredictable URL

**Vulnerability:** Admin path hidden in client-side HTML source code

**How I found it:**
Right-clicked the page and opened the browser inspect tool. Reviewed
the HTML source and found the admin panel path embedded in a script
tag. Navigated directly to that URL and gained full admin access
without authentication.

![Lab 2 - Right click inspect](/appsec-notes/lab2/lab2-right-click-inspect.png)

![Lab 2 - Admin path found in HTML source](/appsec-notes/lab2/lab2-html-source-admin-path.png)

![Lab 2 - Admin panel accessed via URL](/appsec-notes/lab2/lab2-admin-panel-access.png)

![Lab 2 - Admin panel users list](/appsec-notes/lab2/lab2-admin-panel-users.png)

**What I learned:**
Anything sent to the browser is visible to the user — no matter
how hidden it seems. Developers cannot rely on obscure URLs in
client-side code as a security control. If it's in the HTML,
an attacker will find it.

**The Fix:**
Never embed sensitive paths or logic in client-side code.
Access control must be enforced on the server side, not hidden
in the front end. Assume all HTML, JavaScript, and client-side
code is readable by anyone.

**OWASP Reference:** A01 - Broken Access Control
```

