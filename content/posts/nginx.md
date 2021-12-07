---
title: "Nginx"
date: 2021-09-27T20:50:01-05:00
draft: true
---

### What is Nginx

NGINX is open source software for web serving, reverse proxying, caching, load balancing, media streaming, and more. It started out as a web server designed for maximum performance and stability. In addition to its HTTP server capabilities, NGINX can also function as a proxy server for email (IMAP, POP3, and SMTP) and a reverse proxy and load balancer for HTTP, TCP, and UDP servers.

### Why Nginx over Apache?

Both are fantastic web servers, but I choose Nginx because its faster and a bit easier to configure. I only had to add a couple of lines to a single config
file to enable the web server to serve up the `www` directory in all of the users on the system home directories. In Apache this process is done with the use
of sub modules and requires a tiny bit more work to accomplish. 

