# How to install


## Disabling _Hyper-V_ on Windows 10 and 11
If you need to disable Hyper-V on Windows 10 or 11, follow these steps:

### 1. Disable Hyper-V Feature

1. **Open Control Panel:**
   - Press `Win + R`, type `control`, and press `Enter`.

2. **Navigate to Programs:**
   - Go to `Programs` > `Turn Windows features on or off`.

3. **Turn Off Hyper-V:**
   - In the list of Windows features, make sure the `Hyper-V` checkbox is **unchecked**.
   - Click `OK` to apply the changes.

### 2. Modify Boot Configuration

1. **Open Command Prompt as Administrator:**
   - Press `Win + X` and select `Command Prompt (Admin)` or `Windows PowerShell (Admin)`.

2. **Run the Command:**
   - Enter the following command to disable the Hyper-V hypervisor:
     ```bash
     bcdedit /set hypervisorlaunchtype off
     ```

3. **Verify the Change:**
   - You can check the current configuration by running:
     ```bash
     bcdedit /enum {current}
     ```
   - Look for `hypervisorlaunchtype` to ensure it is set to `Off`.

### 3. Restart Your Computer

- Restart your computer to apply the changes.



By following these steps, you will have successfully disabled Hyper-V on your Windows 10 or 11 system.



## Install the guest machine

### 1. Configure the ubuntu vm via vm ware.
!(Pictures/Picture1.png)
### 2. Run vm and install ubuntu…

## Install Necessary Packages on Ubuntu

To set up your Ubuntu guest machine, you need to install some essential packages. Follow these steps:

### 1. Update Package List

```bash
sudo apt-get update
```
### 2. Install Required Packages

```bash
sudo apt install curl git
```
### 3. Install Docker Engine

Follow these steps to install Docker Engine on your Ubuntu guest machine and verify the installation.

1. **Prepare Your System:**
    - Update Package List and Install Dependencies.
     ```bash
    sudo apt-get update
    sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
     ```
2. **Add Docker’s Official GPG Key:**
     ```bash
    sudo mkdir -p /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
     ```
3. **Set Up the Docker Repository:**
     ```bash
    echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
     ```
4. **Update Package List Again:**
     ```bash
    sudo apt-get update
     ```
5. **Install Docker Engine:**
     ```bash
    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
     ```
6. **Add Your User to the Docker Group:**
     ```bash
    sudo groupadd docker
    sudo usermod -aG docker $USER
    newgrp docker
     ```
7. **To check if the engine is installed correctly, run the following command:**
     ```bash
    docker run hello-world
     ```
### 4. Install virtualbox in a guest machine 

1. **Download the appropriate package for your Linux distribution from the [VirtualBox Linux Downloads](https://www.virtualbox.org/wiki/Linux_Downloads) page.**





