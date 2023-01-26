# Pluralsight-Labs

Over the last several years, some of my Pluralsight courses have used a PowerShell module called `PS-Autolab-Env`. This module is also known as `PSAutolab`. Technically, it manages a technology generally referred to as `Autolab`. As many of you have discovered, the video for a given course includes instructions for setting up a lab environment that is now obsolete. I am working with Pluralsight to update course video with something to give you correct information.

The PSAutoLab module is now owned by Pluralsight and active maintained by me. However, you don't get any files from GitHub. Instead, the module is installed from the PowerShell Gallery. In order to use the module, you need to meet the following requirements.

## Requirements

+ A Windows 10 desktop that you have admin rights to. This should be a physical machine running Windows 10 Pro or Enterprise. Windows 10 Home won't work Running in an Azure virtual machine will not work. Running in a virtual machine won't likely work unless you enable nested virtualization. I would avoid it.
+ You need to have 16GB of memory
+ You should have 100GB of free drive space on an internal drive.
+ Your computer must support virtualization. You might have to enable it in the BIOS.
+ You must be able to use and manage PowerShell remoting.

## Installation

Open an elevated Windows PowerShell session, that is, `Run As Administrator` and run:

```powershell
Install-Module PSAutolab -force
```

Answer *Yes* when prompted. **Do not install in PowerShell 7 or PowerShell Core.**

At the prompt run:

```powershell
Setup-Host
```

This will install Autolab to your C:\ drive under `C:\Autolab`. If the setup needs to install the Hyper-V feature, you need to reboot and re-open an elevated PowerShell prompt.

## Lab Setup

In Windows PowerShell change directories to the Configurations directory.

```powershell
cd c:\autolab\configurations
dir
```

The directory listing shows the available lab configurations. For many of my courses you will change locations to `PowerShellLab`.

```powershell
cd PowerShellLab
```

In the course you are watching, you can ignore most of the setup instructions except for the end when I tell you what configuration to use. A few courses, such as *Your First Day with PowerShell* use the Windows10 configuration, so change directories to that folder.

From here, you can run an unattended setup.

```powershell
PS C:\Autolab\Configurations\PowerShellLab\> Unattend-Lab
```

The first time you setup a lab, the module will download ISO files from Microsoft. This will take some time. The actual lab setup shouldn't take more than 20 minutes or so.

## More Information

For more details about the PSAutolab module, go to [the module's README page](https://github.com/pluralsight/PS-AutoLab-Env/blob/master/README.md). If necessary, follow the link to detailed documentation instructions. Beginning in version 4.17.0 of the module, you can also run `Open-PSAutolabHelp` to view a PDF version of all documentation.

If you encounter a problem getting the module installed or a lab setup, please post in the [Issues](https://github.com/pluralsight/PS-AutoLab-Env/issues) of the GitHub repository.
