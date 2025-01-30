#!/bin/bash

# System Information
echo "System Information:"
echo "------------------"
echo "Current Date and Time: $(date)"
echo "Hostname: $(hostname)"
echo "Operating System and Version:"
cat /etc/os-release

echo "System Uptime: $(uptime)"
echo "Current User: $(whoami)"
echo ""

# File and Directory Management
echo "File and Directory Management:"
echo "----------------------------"
echo "Files in /tmp/mytempdir:"
ls -l "/tmp/mytempdir"

echo "Disk usage of /tmp/mytempdir:"
du -sh "/tmp/mytempdir"
echo ""

# Process Management
echo "Process Management:"
echo "--------------------"
ps aux | head -n 10
echo "Listing first 10 running processes..."
echo ""

# User and Group Management
echo "User and Group Management:"
echo "--------------------------"
echo "Current user groups: $(groups)"
echo ""

# Networking
echo "Networking:"
echo "-----------"
echo "Network Interfaces:"
ip addr
echo ""

echo "Listening Network Sockets:"
netstat -lntp | head -n 10
echo ""

# System Resources
echo "System Resources:"
echo "------------------"
df -h
echo ""

free -h
echo ""

echo "Script execution completed."
