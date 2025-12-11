# 🚀 Installing VMware Workstation Player & Ubuntu 22.04 on Windows 11

This guide explains how to install **VMware Workstation Player** on **Windows 11** and how to create a virtual machine running **Ubuntu 22.04 LTS**.

---

## 📌 Prerequisites

Before starting, ensure the following:

- Windows 11 PC with **at least 8 GB RAM**
- **Virtualization enabled** in BIOS (Intel VT-x or AMD-V)
- **20–40 GB free disk space**
- Stable internet connection

---

## 1️⃣ Download VMware Workstation Player

1. Visit the following download page:  
   👉 https://www.techspot.com/downloads/1969-vmware-player.html
2. Click **Download for Windows**.
3. Save the installer file, which looks like:  
   `VMware-player-17.x.x-xxxxxxx.exe`

---

## 2️⃣ Install VMware Workstation Player

1. Run the downloaded `.exe` file.
2. If prompted by Windows, click **Yes** to allow installation.
3. In the setup wizard:
   - Accept the **End User License Agreement**
   - Keep default installation settings unless you prefer otherwise
   - (Optional) Disable **Check for product updates on startup**
4. Click **Install** to begin.
5. When complete, click **Finish**.

The first time you open VMware Player:

- Select **Use VMware Workstation Player for free for non-commercial use**
- Click **Continue**

---

## 3️⃣ Download Ubuntu 22.04 ISO Image

1. Go to the Ubuntu download page:  
   👉 releases.ubuntu.com/22.04
2. Download the ISO file, typically named:  
   `ubuntu-22.04.5-desktop-amd64.iso`

---

## 4️⃣ Create a New Ubuntu Virtual Machine

1. Open **VMware Workstation Player**
2. Click **Create a New Virtual Machine**
3. Choose:  
   **Installer disc image (ISO)** → select your downloaded Ubuntu ISO file
4. VMware will automatically detect Ubuntu and enable Easy Install.
5. Enter your Ubuntu username and password if prompted.
6. Configure VM resources:
   - **Memory (RAM):** 4–8 GB  
   - **Processors:** At least 2 CPU cores  
   - **Disk size:** 45.0 GB (recommended)  
   - **Disk format:** Split into multiple files (optional)
7. Click **Finish** to create the VM.

---

## 5️⃣ Install Ubuntu 22.04 in the Virtual Machine

After launching the VM:

1. Select **Install Ubuntu**
2. Choose your keyboard layout
3. Select **Normal Installation**
4. For *Installation Type*, choose:  
   **Erase disk and install Ubuntu**  
   *(This affects only the virtual disk, not your actual Windows system.)*
5. Select your timezone
6. Create your Ubuntu user account
7. Wait for installation to complete
8. Restart the VM when prompted

---

## 6️⃣ Install VMware Tools (Recommended)

**VMware Tools** improves your VM performance:

- Better display resolution (auto-resize)
- Clipboard sharing (copy/paste)
- Drag-and-drop support
- Smoother mouse control

Ubuntu 22.04 usually installs VMware Tools automatically.

If not:

1. In VMware Player:  
   **Player > Manage > Install VMware Tools**
2. Inside Ubuntu, open the mounted virtual CD
3. Extract and run the installer following the instructions
4. Reboot the VM

---

## ✔️ Installation Complete!

You now have:

- VMware Workstation Player installed on Windows 11  
- A fully functional Ubuntu 22.04 virtual machine  

---

## 🧩 Optional Enhancements

### 🔹 Enable Shared Folders
1. Player → Settings → **Options**  
2. Select **Shared Folders**
3. Enable it and choose a Windows folder to share

### 🔹 Enable Copy/Paste Between Host and VM
Ensure VMware Tools is installed.

### 🔹 Improve Performance
- Increase CPU cores or RAM
- Switch to **NVMe** virtual disk (if available)
- Use SSD storage for faster VM performance

---


