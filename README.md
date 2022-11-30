# Adding Plausible analytics script to Mastodon via Nginx

Using a filter you can replace any part of a page directly from nginx conf. Here we are replacing the closing `</body>` with the analytics script, followed by `</body>`. This effectively injects the script before the end of the page. 

You could also replace `</head>` if you prefer to load the script sooner.

## A note about Mastodon and analytics

One of the strengths of mastodon and FOSS in general is enhanced privacy and less tracking. However, nstance owners might use some analytics to track the performance and security of their servers, for example in case of spikes of traffic, unusual number of password reset attempts etc.
Using Google Analytics is out of the question, on the base of principle, but there are much more respectful ways of providing analytics. 

Plausible calls themselves _Simple and privacy-friendly_ so I opted to use it.

Since mastodon out of the box doesn't provide a way to inject a js snippet (used for analytics), at the moment only allowing [custom css](https://github.com/bpawel-bclub/mastodon_aurora), I had to find another way and this nginx filter proved to work.

## Creadits
[Saman Baboli](https://samanbaboli.medium.com/modify-html-pages-on-the-fly-using-nginx-2e7a2d069086)
[Plausible docs](https://plausible.io/docs/proxy/guides/nginx)
[Nginx docs](http://nginx.org/en/docs/http/ngx_http_sub_module.html)

---

# License: MIT

Copyright (c) Pawel Siwczak 2022

Permission to use, copy, modify, and distribute this work 
for any purpose with or without fee is hereby granted,
provided that the above copyright notice and 
this permission appear in all copies. 

This material is provided "as is", with absolutely no warranty 
expressed or implied. Any use is at your own responsibility.
