---
title: "cookie_boi: Client-Side Control of Browser Cookies"
date: 2019-12-11
cover: 
  image: "/cookie-boi/cover.png"
---

### What it is
cookie_boi is a proof-of-concept client-side program to automate the temporary deletion of sensitive cookies without imposing a significant burden to the user, and no burden at all to web application developers or browser developers. 

![Diagram](/cookie-boi/cookieboi-demo.png)

### How it works
When cookie_boi is installed and enabled, the user is automatically “signed out” from a web application by filtering out cookies from requests that contain cookies after 1 hour of inactivity. The name, value, and domain of the authentication cookie is saved to a separate file called the “Pepperidge Farm” that is managed solely by scripts in cookie boi and is unrelated to the browser’s implementation for cookies. At this point, from the perspective of the web application server, the user is still signed in and the authentication cookie value is still valid.

When the user returns to the web application, cookie_boi will request a user action, such as a keypress, to reauthenticate/refresh the cookie. Cookie_boi will restore the authentication cookie from the “Pepperidge Farm” by extending the timeout of the cookie. By the standard implementation of cookies by the browser, the authentication cookie will automatically be attached to the user’s request to the web application, cookie boi will not filter the request, and the user will be authenticated as usual.

Here's a diagram of how it works:

![Diagram](/cookie-boi/CookieBoiNetwork.png)

Find the repo for our project at https://github.com/milanb17/cookie_boi.