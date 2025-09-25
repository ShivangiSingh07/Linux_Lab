 # Process Management in linux 

## 1️⃣ ps aux


Explanation:
```bash
 a → show processes for all users.

 u → show user/owner of process.

 x → show processes not attached to a terminal.
```

### 📷 Output Snapshot:

![SS1](<WhatsApp Image 2025-09-25 at 11.46.47_111421e7.jpg>)

## 2️⃣ Process Tree 🌳

### Command: 

```bash
pstree -p
```
➡️ Shows parent- child relationships.


### 📷 Output Snapshot:

![SS2](<WhatsApp Image 2025-09-25 at 11.46.50_6353f38d.jpg>)


## 3️⃣ Real-Time Monitoring

### Command: 

```bash 
top 
``` 
 ➡️ Press q to quit.

### 📷 Output Snapshot: 

![ss3](<WhatsApp Image 2025-09-25 at 11.46.53_d7bddf70.jpg>)

 

##  4️⃣ Adjust Process Priority



 ♦️ Start a process with low priority:

```bash 
  nice -n 10 sleep 300 &
  ``` 

 ➡️ PID = `3248` is running in background with nice value 10.

  ### 📷 Output Snapshot:

![ss4](<WhatsApp Image 2025-09-25 at 11.46.57_58bb2377.jpg>)



♦️ Change priority of running process: 

```bash
renice -n -5 -p 3248
```
➡️ Now process runs with higher priority.

### 📷 Output Snapshot:
![ss4](<WhatsApp Image 2025-09-25 at 11.47.00_ea4b6fe5.jpg>)


## 5️⃣ CPU Affinity (Bind Process to CPU Core)

### Command:

```bash
 taskset -cp 3369
``` 

### 📷 Output Snapshot:

![ss5](<WhatsApp Image 2025-09-25 at 11.47.03_eb2e3c78.jpg>)

* pid 3369's current affinity list: 0-3

* Shows process is allowed on cores `0,1,2,3`.

♦️ Restrict to core 1 only: 

```bash
taskset -cp 1 3369
``` 

### 📷 Output Snapshot:

![ss6](<WhatsApp Image 2025-09-25 at 11.47.12_4b348e36.jpg>)

## 6️⃣ I/O Scheduling Priority

### Command: 

```bash
ionice -c 3 -p 3369
``` 

### 📷 Output Snapshot:

![ss7](<WhatsApp Image 2025-09-25 at 11.47.17_0c7e7a01.jpg>)


➡️ Class 3 (idle) → Process only gets I/O when system is idle.


## 7️⃣ File Descriptors Used by a Process

### Command:

```bash
 lsof -p 3477 | head -5 
``` 

### 📷 Output Snapshot:

![ss8](<WhatsApp Image 2025-09-25 at 11.47.22_e00d31bc.jpg>)


## 8️⃣  Trace System Calls of a Process

### Command: 

```bash
strace -p 3477
```

### 📷 Output Snapshot:

![ss9](<WhatsApp Image 2025-09-25 at 11.47.25_ecbd5cea.jpg>)


➡️ Great for debugging.


## 9️⃣ Find Process Using a Port

### Command:

```bash
sudo fuser -n tcp 8080
``` 

### Output Snapshot:

---


 ➡️ PID is using port 8080.

## 🔟 Per-Process Statistics

### Command:

```bash
 pidstat -p 3636 2 3
 ```

### 📷 Output Snpashot:

![ss10](<WhatsApp Image 2025-09-25 at 11.47.25_ea0492aa.jpg>)

- Shows CPU usage every 2 seconds, 3 times.


## ⏸️ Control Groups (cgroups) for Resource Limits


### Create a new cgroup:

```bash
sudo cgcreate -g cpu,memory:/testgroup
```
 
 Limit CPU and Memory: ---

 


