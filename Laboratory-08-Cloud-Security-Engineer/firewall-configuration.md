# Firewall Configuration Guide

**Laboratory 08 – Cloud Security Engineer**

## Introduction

This document explains the firewall configuration used to protect an Ubuntu server hosting an Nginx web application.

The Uncomplicated Firewall (UFW) is used to manage incoming and outgoing network traffic and restrict access to necessary services.

## 1. Deploying the Web Application

The following command creates an Nginx container named `secure-web-app` and publishes the application on port 8080.

```bash
docker run -d --name secure-web-app -p 8080:80 nginx
```

To verify that the container is running:

```bash
docker ps
```

To test the web application:

```bash
curl http://localhost:8080
```

A successful request returns the default Nginx HTML page containing the message:

```text
Welcome to nginx!
```

## 2. Allowing SSH Access

Before enabling the firewall, SSH access must be allowed to reduce the risk of losing remote administrative access.

```bash
sudo ufw allow ssh
```

This command creates a firewall rule that permits SSH traffic, normally using TCP port 22.

## 3. Configuring Default Firewall Policies

Block all incoming connections by default:

```bash
sudo ufw default deny incoming
```

Allow outgoing connections:

```bash
sudo ufw default allow outgoing
```

The Default Deny policy blocks incoming connections unless a firewall rule explicitly allows them.

## 4. Enabling the Firewall

Activate UFW using:

```bash
sudo ufw enable
```

If prompted to continue, enter `y`.

Verify the firewall configuration:

```bash
sudo ufw status verbose
```

The expected configuration includes:

```text
Status: active
Default: deny (incoming), allow (outgoing)
```

## 5. Allowing TCP Port 8080

To permit web application traffic through TCP port 8080, execute:

```bash
sudo ufw allow 8080/tcp
```

This creates a firewall rule allowing incoming TCP connections on port 8080.

## 6. Verifying Firewall Rules

Display the configured firewall rules:

```bash
sudo ufw status numbered
```

The firewall should list rules permitting SSH and TCP port 8080.

Test the Nginx application:

```bash
curl http://localhost:8080
```

A successful response confirms that the application is responding locally.

**Technical Note:** Docker-published ports may bypass ordinary UFW incoming rules. Therefore, a successful localhost request alone does not prove that UFW is enforcing external access restrictions. External network testing and appropriate Docker firewall integration are necessary for production security verification.

## 7. Importance of Allowing SSH Before Enabling UFW

If `sudo ufw enable` is executed before allowing SSH, the firewall may block remote SSH connections and prevent administrators from accessing the server remotely.

## 8. Firewall Configuration Summary

| Service | Port | Protocol | Configuration |
|---|---|---|---|
| SSH | 22 | TCP | Allow |
| Nginx Application | 8080 | TCP | Allow |
| Other Incoming Traffic | Other ports | Any | Default Deny |
| Outgoing Traffic | All | Any | Default Allow |

## Conclusion

Configuring UFW with a Default Deny policy is an important step toward securing a Linux server.

By allowing only necessary services and reviewing firewall rules, cloud administrators can reduce unnecessary network exposure and improve system security.
