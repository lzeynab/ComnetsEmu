# _How to install_
## Disabling _Hyper-V_ on Windows 10 and 11

If you need to disable Hyper-V on Windows 10 or 11, follow these steps:

## 1. Disable Hyper-V Feature

1. **Open Control Panel:**
   - Press `Win + R`, type `control`, and press `Enter`.

2. **Navigate to Programs:**
   - Go to `Programs` > `Turn Windows features on or off`.

3. **Turn Off Hyper-V:**
   - In the list of Windows features, make sure the `Hyper-V` checkbox is **unchecked**.
   - Click `OK` to apply the changes.

## 2. Modify Boot Configuration

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

## 3. Restart Your Computer

- Restart your computer to apply the changes.

By following these steps, you will have successfully disabled Hyper-V on your Windows 10 or 11 system.

# Install the guest machine

## 1. Configure the ubuntu vm via vm ware.
![Sample Image](C:\Users\Zeynab\Desktop/Picture1.png)
## 2. Run vm and install ubuntu…

# Install Necessary Packages on Ubuntu

To set up your Ubuntu guest machine, you need to install some essential packages. Follow these steps:
Follow these instructions to install Docker Engine on your Ubuntu guest machine

## 1. Update Package List

```bash
sudo apt-get update
```
## 2. Install Required Packages

```bash
sudo apt install curl git
```
