#!/bin/bash
timedatectl set-timezone Asia/Seoul
sed -i 's/#Port 22/Port 2025/g' /etc/ssh/sshd_config
sed -i 's|.*PasswordAuthentication.*|PasswordAuthentication yes|g' /etc/ssh/sshd_config
systemctl restart sshd
echo 'Skill53##' | passwd --stdin ec2-user
