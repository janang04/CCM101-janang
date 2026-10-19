# Laboratory 08 - Cloud Security Engineer

## Mission Overview

This laboratory activity focuses on securing an Ubuntu server using the Uncomplicated Firewall (UFW). An Nginx web application is deployed using Docker, and firewall rules are configured to allow SSH and HTTP application traffic while denying other incoming host connections by default.

## Objectives

- Understand the Principle of Least Privilege and Attack Surface.
- Deploy an Nginx web application using Docker.
- Perform a basic audit of the server and firewall rules.
- Configure UFW with a Default Deny policy.
- Allow SSH on port 22 and application traffic on port 8080.
- Document firewall configurations using Markdown.

## Commands Executed

```bash
docker --version
docker run -d --name secure-web-app -p 8080:80 nginx:latest
docker ps
curl http://localhost:8080
sudo ufw allow ssh
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
sudo ufw status verbose
sudo ufw allow 8080/tcp
sudo ufw status numbered
curl http://localhost:8080
```

## Skills Learned

- Docker container deployment
- Linux command-line operations
- Firewall configuration using UFW
- Default Deny security policies
- Network port management
- Secure remote administration concepts
- Application connectivity testing
