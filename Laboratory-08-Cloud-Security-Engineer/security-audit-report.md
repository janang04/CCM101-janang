
# Security Audit Report

## Mission 8: The Cloud Security Engineer

### 1. Principle of Least Privilege (PoLP)

The Principle of Least Privilege means giving users and applications only the permissions they need to perform their tasks. It is important in cloud computing because limiting access reduces the risk of unauthorized actions, data exposure, and account misuse.

### 2. Attack Surface

An attack surface refers to all the possible entry points that attackers could use to access a virtual machine or server. These include open network ports, running services, software vulnerabilities, and exposed applications that may be targeted by attackers.

### 3. Default Deny Policy

A Default Deny Policy blocks incoming network traffic unless a specific rule allows it. This is safer than blocking individual attackers because unauthorized connections are rejected by default, even when the administrator does not know the attacker's identity.

## Security Audit Commands

```bash
docker ps
sudo ufw status verbose
sudo ufw status numbered
```

## Security Recommendations

- Allow only the network ports required by the application.
- Protect remote administration through secure SSH access.
- Keep the operating system and applications updated.
- Review firewall rules regularly.
- Avoid exposing database services directly to the public internet.
