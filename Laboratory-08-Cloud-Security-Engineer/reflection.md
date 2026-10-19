# Mission 8 – Personal Reflection

**Laboratory 08: The Cloud Security Engineer**

In this laboratory activity, I learned the importance of securing cloud servers using a host-based firewall. A host-based firewall provides an additional layer of protection by controlling network traffic directly on the server. Even if an attacker bypasses the physical network perimeter, the firewall can still restrict unauthorized connections based on configured security rules.

I also realized that managing open network ports is important in reducing a server's attack surface. Every unnecessary open port may expose a service that attackers could target. By allowing only essential ports, such as SSH port 22 and the application's port 8080, administrators can reduce unnecessary network exposure and improve server security.

In a real enterprise environment, leaving a database port such as MySQL port 3306 accessible to the public internet can create serious security risks. Attackers may attempt brute-force attacks, exploit vulnerabilities, or gain unauthorized access to sensitive information. Database services should therefore be restricted to trusted networks and authorized applications.

Completing this mission helped me understand that a server can become vulnerable when security configurations are overlooked. Deploying an application is not enough because administrators must also protect the environment where it operates. I learned that security should be considered throughout the deployment and maintenance process.

Looking at my GitHub Cloud Computing Portfolio from Laboratory 1 to Laboratory 8, I can see how the activities cover different areas of cloud computing. These include cloud infrastructure, containerization, deployment, monitoring, and security. Each mission introduces new responsibilities and helps connect theoretical knowledge with practical Linux administration tasks.

Overall, this laboratory activity improved my understanding of firewall configuration, network access control, and cloud security principles. It taught me that protecting cloud infrastructure requires careful planning, proper configuration, and continuous monitoring to maintain a secure and reliable environment.
