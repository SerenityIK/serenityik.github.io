---
layout: post
title: "Nginx not loading static files"
date: 2020-12-20 22:04:30 +0300
categories: nginx, static files
---
If nginx can't load static files you need to change home directory owner and permissions:

`sudo chown -R <user>:nginx /home` - recursively changing owner to your user and nginx group

`sudo chmod -R 0755 /home` - recursively changing permissions of home directory to rwxrwxrwx

Restart nginx service:

`sudo systemctl restart nginx`
