---
title: "Cloudflare"
date: 2021-10-08T20:50:26-05:00
draft: false
---

### What is Cloudflare

Cloudflare, Inc. is an American web infrastructure and website security company that provides content delivery network and DDoS mitigation services. They also happen to provide some of the best `FREE` DNS for your own domains. They offer a slew of other product lines (most for free). The login screen for this blog is one of those features. 

### Cloudflare Access

Since this server sits behind a firewall that does not allow ports 80 or 443 to pass I had to get creative to allow access to it via your browser. This is where cloudflare access comes into the picture. I installed the cloudflared agent on the server which, once configured, sets up a reverse tunnel proxy to the cloudflare infrascutre. When you make the HTTPS request to this site, it goes to cloudflare, who then makes the request on your behalf to the proxy tunnel landing you at the nginx server that runs on this server. This server could get a way without even haven a public IP address and this tunnel proxy would function properly so long as this server can make requests _out_ to the internet. It even presists over IP address changes as we've recently seen when the IP for this server had to change. No further changes were required and the link just works. 

Check it out! https://www.cloudflare.com/teams/access/