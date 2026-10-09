# Mission Reflection: The Cloud Operations Engineer

This laboratory activity helped me understand why monitoring is an important responsibility of a Cloud Operations Engineer. I learned that checking the host server's resources is necessary even when containers are running properly. A container may be working, but the host can still experience low memory, high CPU usage, or insufficient disk space. These problems can affect application performance and may cause services to stop working.

The `docker logs` command is useful when a user reports that they cannot log into a web application. By checking the logs, an engineer can identify errors, failed requests, and other events that occurred when the user tried to access the application. These records can provide clues about the cause of the problem and help the engineer decide what to investigate next.

I also learned the difference between monitoring logs and monitoring metrics. Logs contain records of specific events, such as HTTP requests and error messages. Metrics provide numerical information about system performance, including CPU usage, memory consumption, and network activity. Both are important because logs help explain what happened, while metrics help show how the system is performing.

Large enterprise companies may use monitoring platforms such as Prometheus and Grafana to observe thousands of containers. Prometheus can collect and store time-series metrics, while Grafana can display those metrics through dashboards and visualizations. These tools help operations teams identify unusual behavior and investigate potential performance problems across many services.

Before this activity, I had a basic understanding of Linux commands and Docker. Through the laboratory exercises, I practiced checking system resources, deploying an Nginx container, generating HTTP requests, examining application logs, and observing container metrics. I realized that troubleshooting should be based on actual evidence instead of guessing. This experience improved my understanding of cloud operations and showed me the importance of continuous monitoring, accurate documentation, and systematic problem-solving.

Overall, this laboratory activity gave me a better foundation for understanding how cloud engineers maintain reliable and efficient applications.
