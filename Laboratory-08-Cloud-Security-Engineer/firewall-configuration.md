# Firewall Configuration

## Mission 8: The Cloud Security Engineer

### 1. Allow SSH Access

```bash
sudo ufw allow ssh
```

This command allows SSH connections on port 22 so administrators can remotely manage the server.

### 2. Configure Default Firewall Policies

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

These commands block incoming traffic by default while allowing outgoing traffic from the server.

### 3. Enable the Firewall

```bash
sudo ufw enable
```

This command activates UFW and applies the configured firewall rules.

### 4. Verify Firewall Status

```bash
sudo ufw status verbose
```

This command displays the firewall status, default policies, and active rules.

### 5. Allow Web Application Traffic

```bash
sudo ufw allow 8080/tcp
```

This command adds a rule to allow incoming TCP traffic on port 8080, which is used by the Nginx application.

### 6. View Numbered Firewall Rules

```bash
sudo ufw status numbered
```

This command displays the configured firewall rules with their corresponding numbers.

### 7. Test the Web Application

```bash
curl http://localhost:8080
```

This command checks whether the Nginx web application responds locally on port 8080.

### 8. Importance of Allowing SSH Before Enabling UFW

If `sudo ufw enable` is executed before `sudo ufw allow ssh`, the administrator may lose remote SSH access to the server because incoming SSH connections could be blocked.

## Conclusion

The UFW configuration follows the Default Deny approach by allowing SSH and the required application port while denying other incoming host traffic by default. Additional firewall controls may be necessary for Docker-published ports because Docker manages its own forwarding rules.
