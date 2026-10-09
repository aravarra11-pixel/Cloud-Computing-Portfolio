# Laboratory Activity 7: The Cloud Operations Engineer

## Mission Overview
This laboratory activity focuses on Linux system monitoring, Docker container deployment, application logging, and real-time resource monitoring using the KillerCoda Playground.

## Objectives
- Check the host system's RAM, disk capacity, and CPU activity.
- Deploy an Nginx web server using Docker.
- Generate successful HTTP requests and an intentional HTTP 404 error.
- Inspect application logs and container resource metrics.
- Document the results in Markdown and maintain a GitHub portfolio.

## Monitoring Commands Executed
| Command | Purpose |
|---|---|
| `free -h` | Check memory usage |
| `df -h /` | Check root filesystem storage |
| `top` | Observe CPU activity and running processes |
| `docker run -d --name client-website -p 8080:80 nginx` | Deploy the Nginx container |
| `curl http://localhost:8080/` | Test the web server |
| `curl http://localhost:8080/hidden-admin-page` | Generate an HTTP 404 response |
| `docker logs client-website` | Inspect application logs |
| `docker stats` | Monitor container resource consumption |

## Skills Learned
- Linux system resource monitoring
- Docker container deployment
- HTTP request testing and error identification
- Application log analysis
- Container performance monitoring
- Markdown documentation and GitHub portfolio management

## Evidence
Screenshots for each checkpoint are stored in the `screenshots/` folder.
