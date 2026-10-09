# System Baseline Report

## Objective
To check the baseline health of the Linux host before deploying the Nginx web server.

## Memory Check
- Total RAM: [Enter the total RAM shown by `free -h`]
- Available RAM: [Enter the available RAM shown by `free -h`]

## Disk Check
- Root filesystem total capacity: [Enter the Size value from `df -h /`]
- Available disk space: [Enter the Avail value]
- Disk usage: [Enter the Use% value]

## CPU and Process Check
Command executed: `top`

Observation: [Describe the CPU load and running processes you observed.]

## Why Disk Monitoring Is Important
Checking disk space before a traffic surge helps prevent service interruptions caused by insufficient storage for application logs, temporary files, and other data.
