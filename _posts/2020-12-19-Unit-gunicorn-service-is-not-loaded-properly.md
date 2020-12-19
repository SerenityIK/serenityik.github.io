---
layout: post
title: "Unit gunicorn.service is not loaded properly: Exec format error."
date: 2020-12-19 23:05:00 +0300
categories: gunicorn server, systemd service, nginx sockets, gunicorn error, permission denied
---
If Gunicorn service can't connect to .sock file while working with nginx via socket, and returning error: "OSError: [Errno 13] Permission denied:" you just need to change permissions for your project folder to rwxrwxrwx

Just execute command `sudo chmod 0777 /usr/share/nginx/html/<your_project_folder>` and restart service `sudo systemctl restart gunicorn.service`.
