# Laboratory 08 - Mission Reflection

Completing Laboratory Activity 8 helped me understand the importance of protecting cloud servers through proper firewall configuration. I learned that deploying an application is not enough because securing the server and controlling network access are also important responsibilities of a Cloud Security Engineer.

A host-based firewall protects a server by filtering traffic directly at the operating system level. Even if an attacker bypasses the physical network perimeter, the host firewall can still block unauthorized connections according to its configured rules. This adds another layer of protection and supports the principle of defense in depth.

Managing open network ports is also important because every unnecessary exposed service can become a possible entry point for attackers. By allowing only the required ports, administrators can reduce the server's attack surface and limit opportunities for unauthorized access. In this activity, I studied the importance of allowing SSH on port 22 and application traffic on port 8080.

In a real enterprise environment, leaving MySQL port 3306 accessible to the public internet can create serious security risks. Attackers may attempt password guessing, exploit database vulnerabilities, or gain unauthorized access to sensitive information. Database connections should therefore be restricted to trusted applications and authorized systems.

This mission changed my perspective because I realized how easily a poorly configured server could become vulnerable. I also learned that security requires careful planning, regular monitoring, and correct configuration rather than simply installing software.

My GitHub Cloud Computing portfolio shows my progress across the eight laboratory missions. Each activity represents a different practical skill, including deployment, operations, and security. Organizing my files, commands, and screenshots helps me review what I learned and demonstrate my technical development. Overall, this activity strengthened my understanding of cloud security and reminded me that protecting systems is an ongoing responsibility.
