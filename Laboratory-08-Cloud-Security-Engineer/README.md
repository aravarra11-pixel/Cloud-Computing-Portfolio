# Laboratory 08 – Cloud Security Engineer

**Course:** CCM101 – Cloud Computing  
**Laboratory Activity:** 8  
**Mission:** The Cloud Security Engineer  
**Company:** CloudNova Technologies

## Mission Overview

This laboratory activity focuses on securing a Linux server using the Uncomplicated Firewall (UFW). The mission involves deploying an Nginx web application using Docker, auditing network ports, configuring firewall policies, and allowing only necessary network traffic.

The activity demonstrates the importance of protecting cloud infrastructure against unauthorized access and potential security threats.

## Objectives

- Understand the Principle of Least Privilege.
- Identify and reduce the attack surface of a server.
- Deploy an Nginx web application using Docker.
- Configure the UFW firewall on Ubuntu Linux.
- Apply a Default Deny policy for incoming traffic.
- Allow SSH connections through port 22.
- Allow HTTP application traffic through port 8080.
- Verify firewall rules using Linux commands.
- Document cloud security configurations using Markdown.

## Tools and Technologies Used

- KillerCoda Ubuntu Playground
- Docker
- Nginx Web Server
- Linux Terminal
- UFW Firewall
- GitHub
- Markdown

## Commands Executed

### Deploy Nginx Web Application

```bash
docker run -d --name secure-web-app -p 8080:80 nginx
docker ps
curl http://localhost:8080
```

### Configure Firewall

```bash
sudo ufw allow ssh
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
sudo ufw status verbose
```

### Allow Port 8080

```bash
sudo ufw allow 8080/tcp
sudo ufw status numbered
curl http://localhost:8080
```

## Security Configuration

The firewall configuration uses a Default Deny policy to block incoming connections unless they are explicitly permitted.

SSH traffic is allowed for remote administration, while TCP port 8080 is allowed for the Nginx web application.

Outgoing traffic is permitted to support normal server communication.

## Skills Learned

Through this laboratory activity, I learned how to deploy a containerized web application and configure basic Linux firewall rules.

I also gained an understanding of how network security policies, access restrictions, and port management help protect cloud infrastructure.

## Screenshots

### Vulnerable Application Running

![Vulnerable Application](screenshots/vulnerable-app-running.png)

### Firewall Activated

![Firewall Activated](screenshots/firewall-activated.png)

### Firewall Port Allowed

![Firewall Port Allowed](screenshots/firewall-port-allowed.png)

## Conclusion

This laboratory activity demonstrates how firewall configuration contributes to cloud security. By implementing restrictive network policies and allowing only necessary services, administrators can reduce unnecessary exposure and improve the security of Linux servers.
