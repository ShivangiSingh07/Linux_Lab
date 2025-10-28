# SSh Setup Guide

This guide explains how to install and use SSH on Linux for secure remote access and file transfer. It includes setup, troubleshooting, and SCP usage with clear explanations.

### Prerequisites

- Ubuntu sustem
- terminal access
- Two machines connected to the same network (for testing SSH)

### Steps Followed

1. Install SSH

Install the OpenSSH server package on the machine you want to connect to:

```bash
sudo apt update
sudo apt install openssh-server. 
``` 

### Check SSH Status

- to verify that SSH is running, use the following command:

```bash
sudo systemctl status ssh
```

### Restart SSH (if needed)

If the SSH service is not running, or if you've made changes to the SSH configuration file (`/etc/ssh/sshd_config`), you need to restart the SSH service to apply those changes. Restarting ensures the new settings take effect and the service runs properly.

```bash
sudo systemctl restart sssh
```

### Enable SSH on Boot

By default, SSH may not start automatically when the system reboots. To ensure that the SSH service is always available after a restart, you can enable it to start on boot.

```bash
sudo systemctl enable ssh
```

### Find IP Address

To connect to this machine from another device using SSH, you need to know its IP address on the network.

```bash
ip a
```
## Troubleshooting SSH

### Allow SSH Through Firewall

If your system has a firewall enabled (like `ufw` on Ubuntu), it may block incoming SSH connections by default. To allow SSH traffic through the firewall, you need to open port 22, which is the default SSH port.

```bash
sudo ufw allow ssh
sudo ufw wenable
```

### Check SSH Port

By default, SSH uses port 22. If you're having trouble connecting or want to use a custom port (for security or conflict reasons), you can check or change the port in the SSH configuration file.

```bash
sudo nano /etc/ssh/sshd_config
```

### Restart SSH After Config Change

If you make any changes to the SSH configuration file (`/etc/ssh/sshd_config`), such as changing the port number or disabling password login, those changes won’t take effect until you restart the SSH service.

```bash
sudo systemctl restart ssh
```

## SCP File Transfer

### Send File to Another Machine

To transfer a file from your current machine to another Linux machine over the network, use the `scp` (Secure Copy) command. This works over SSH, so make sure SSH is set up and running on both machines.

```bash
scp file.txt username@remote_ip:/home/username/
```

### Recieve File from Another Machine

To download a file from a remote Linux machine to your current system, use the `scp` (Secure Copy) command. This works over SSH, so make sure SSH is running on the remote machine and you have its IP address.

```bash
scp username@remaote_ip:/home/username/file.txt
```



