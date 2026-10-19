# Security Audit Report

**Laboratory 08 – Cloud Security Engineer**

## Introduction

Cloud security is important because servers connected to networks may be exposed to unauthorized access and cyberattacks. Understanding basic security principles helps administrators identify vulnerabilities and apply appropriate protection measures.

## 1. Principle of Least Privilege (PoLP)

The Principle of Least Privilege is a security concept that gives users and applications only the minimum permissions required to perform their assigned tasks. It is important in cloud computing because limiting permissions reduces the risk of unauthorized access, accidental changes, and potential damage if an account becomes compromised.

## 2. Attack Surface

The attack surface refers to all possible entry points that attackers could use to access or compromise a system. In a virtual machine, these entry points may include open network ports, running services, exposed applications, and weak authentication mechanisms.

## 3. Default Deny Policy

A Default Deny Policy blocks all incoming network traffic unless a specific firewall rule explicitly allows it. This approach is safer because administrators only permit trusted and necessary connections instead of attempting to identify and block every possible malicious source.

## Security Audit Commands

The following commands can be used to inspect running containers, check application connectivity, and review firewall configurations.

```bash
docker ps
curl http://localhost:8080
sudo ufw status verbose
sudo ufw status numbered
```

## Security Recommendations

- Allow only required network ports.
- Use restrictive firewall policies.
- Protect remote administration services.
- Regularly review firewall rules.
- Disable unnecessary network services.
- Monitor network activity for suspicious connections.
- Keep operating systems and applications updated.

## Conclusion

The Principle of Least Privilege, attack surface reduction, and Default Deny policies are important foundations of cloud security.

Applying these principles helps administrators reduce unnecessary exposure and protect cloud infrastructure against potential threats.
