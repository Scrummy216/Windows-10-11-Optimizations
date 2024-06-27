**Basic Windows 10/11 Optimization for Enhanced Performance and Reduced Input Lag**

Uninstalling drivers, the right way
* Before installing a new driver, uninstall it with Display Driver Uninstaller
* Follow the settings according to the picture. Safe mode is recommended but not necessary
* Nvidia Clean installer is a program that lets you download the latest drivers and customize what's going to be included. Also possible to disable telemetry and a bunch of extra things that only runs in the background sending data to Nvidia servers.
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/d7013d9b-c3c4-4620-a01a-8b44bcb2521e)
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/261e7741-e7a2-4ee6-bf5f-98b7aeef34be)
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/5040f3a9-ef40-4696-92c3-ca9291de49fd)
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/779de422-21f3-4307-b9ac-d4303e451d15)
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/e44e7d03-b0c5-4dd4-bdc9-10e8b20d502d)
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/2b8c541f-3b08-411a-a102-2d05fa940e74)
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/c9addab1-596d-4228-a8a4-40edc604d7a2)

# NVIDIA GPU SETTINGS
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/a236e94e-4679-443a-96df-1c330fbb30be)
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/a53f64f5-3583-4b03-8288-81585878cf76)
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/f8d09389-f747-43a4-949c-942c6c668b45)

# AMD GPU SETTINGS
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/23cc1dcf-d34c-4e17-90ee-a28befcb6400)
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/0f92bdfe-4ff4-49f3-80cb-e1340f5a0619)

### Chris Titus debloat settings
* Open powershell (Run as Admin)
* Copy the command below to open the Chris Titus tool
## iwr -useb https://christitus.com/win | iex
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/4edd4eba-debb-49f5-ae28-3926ac03ad8f)

Power Plan: Go to your search bar and type edit power plan If you are on a desktop PC, then click on high performance; if you are on a laptop, we recommend that you do this but keep it on balanced, as this can degrade your laptop battery life.
![image](https://github.com/Scrummy216/Windows-10-11-Optimizations/assets/155396123/8045bf39-777a-4c56-9797-8a3433a8e7c4)

## BCDEdit
Run Command Prompt as admin and paste these italicized commands:
To undo a command in BCDEdit, do bcdedit /deletevalue X (where X is tscsyncpolicy, useplatformtick, etc.)
****`bcdedit /set disabledynamictick yes`**** (Windows 8+)
This command forces the kernel timer to constantly poll for interrupts instead of wait for them; dynamic tick was implemented as a power saving feature for laptops but hurts desktop performance
`bcdedit /set hypervisorlaunchtype off`
Disables the hypervisor which is unneeded on a gaming PC

## Device Manager
Open Device Manager (devmgmt.msc) and disable anything you’re not using. Be careful not to disable something you use. Uninstalling a driver via Device Manager will most likely result in it reinstalling after reboot. In order to completely disable a driver, you must disable it instead of uninstalling. When you disable something in Device Manager, the driver is unloaded. Drivers interrupt the CPU, halting everything until the driver gets CPU time (some drivers are poorly programmed and can cause the system to halt for a very long time [stuttering]). What to disable:

* High Precision event Timer (Disable it only if you will use timer resolution)
* Microsoft Virtual Drive Enumerator (if not using virtual drives)
* NDIS Virtual Network Adapter Enumerator
* Remote Desktop Device Redirector Bus

