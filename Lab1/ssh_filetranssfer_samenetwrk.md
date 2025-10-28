# 🧪 Experiment 1: Transfer a File Using SSH While on the Same Network

---

## 🎯 Objective

To transfer a file from one Linux machine (Sender) to another (Receiver) using SSH and the `scp` command, while both machines are connected to the same local network.

---

## 🛠️ Requirements

- Two Ubuntu machines connected to the same Wi-Fi or LAN
- SSH installed and running on both machines
- A sample file (e.g., `test.txt`) on the Sender machine

---

## 🖥️ Role A: Receiver Machine (Machine that will receive the file)

### Step 1: Install and Start SSH
```bash
sudo apt update
sudo apt install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh
```
• This sets up the SSH server so the machine can accept incoming connections.

### Step 2: Find IP Address
```bash
ip a
```
- Look for the IP address under your active interface (e.g., 192.168.x.y)
- Share this IP with the Sender machine

### Step 3: Confirm SSH is Running
```bash
sudo systemctl status ssh
```
- Make sure it shows active (running)

## 🖥️ Role 2: Sender Machine (Machine that will send the file)

### Step 1: Install and Start SSH (same as Receiver)
```bash
sudo apt update
sudo apt install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh
```
- This ensures the sender can use SSH and SCP commands

### Step 2: Test SSH Connection to Receiver
```bash
ssh username@ip_address
```
- Replace username with the actual user on the Receiver machine
- If prompted, enter the Receiver’s password.

### Step 3: Create a Sample File
```bash
echo "This is a test file." > test.txt
```
- This creates a file named test.txt with sample content.

### Step 4: Send the File Using SCP
```bash
scp test.txt username@ip_address_reciever:/home/username/
```

- test.txt: the file to send.
- username: user on the Receiver machine.
- /home/username/: destination folder on the Receiver.

### ✅ Final Step: Verify File on Receiver

On the Receiver machine:
```bash
ls /home/username/
```
- You should see test.txt listed

### 🧠 Notes
- Both machines must be on the same network
- SSH must be running on the Receiver machine
- If you want to skip password prompts, set up SSH key-based login ↓

## ⚡ Quick Setup: SSH Key-Based Login

To avoid typing your password every time you use SSH or SCP, follow these quick steps:

### On the Sender Machine

1. **Generate SSH Key**
```bash
ssh-keygen
```
- Press Enter through all prompts to accept defaults
- Copy Public Key to Receiver'

```bash
ssh-copy-id username@remote_ip
```
2. **Test SSH Login**
```bash
ssh username@remote_ip
```
- You should connect without a password prompt.

