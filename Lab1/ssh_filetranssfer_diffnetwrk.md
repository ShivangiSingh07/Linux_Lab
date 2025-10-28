# 🧪 Experiment 3: Transfer a File Using SSH Between Machines on Different Networks

---

## 🎯 Objective

To transfer a file from one Linux machine to another using SSH and SCP, when both machines are on **different networks**.

---

## 🛠️ Requirements

- Two Ubuntu machines connected to **different networks**
- SSH installed and running on both machines
- Public IP address or port forwarding set up on the receiver machine
- A sample file (e.g., `report.txt`) on the sender machine

---

## 🌐 Key Concepts

- **Local IPs (like 192.168.x.x)** only work within the same network.
- For different networks, you need the **public IP** of the receiver machine.

---

## 🖥️ Role 1: Receiver Machine (Remote Machine)

### Step 1: Install and Start SSH
```bash
sudo apt update
sudo apt install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh
```
### Step 2: Check SSH Status
Make sure the SSH server is running:
```bash
sudo systemctl status ssh
```
if it's active, you're good to go otherwise restart it.


```bash

sudo systemctl restart ssh

```
### Step 3: Find Public IP Address

This is needed for the sender to reach the receiver across networks.

```bash
curl ifconfig.me
```

or use:

```bash

wget -qO- https://ipecho.net/plain

```
📌 Note: If the receiver is behind a router (NAT), you’ll need to set up port forwarding on the router to forward port  to the receiver’s local IP.

### Step 4: Allow SSH Through Firewall (if enalbed)

```bash

sudo ufw allow ssh
sudo ufw enable

```

## 🖥️ Role 2: Sender Machine (Local Machine)


### Step 1: Install SCP (usually bundled with SSH)

```bash
sudo apt update
sudo apt install openssh-client
```
### Step 2: Transfer the File Using SCP

Use the folllowing syntax:

```bash

scp /path/to/file username@receiver_public_ip:/destination/path

```
Example:


```bash

scp ~/Documents/report.txt shivangi@203.0.xxx.y:/home/shivangi/

```

• 	Replace  with your actual file
• 	Replace  with the receiver’s public IP
• 	Replace  with the desired path on the receiver
You’ll be prompted for the receiver’s password. Once entered, the file will transfer securely.

### 🧪 Verification

On the receiver machine, check if the file arrived:

```bash

ls /home/shivangi/

```
You should see `file.txt`  listed.
