---
id: EOXpAZ1L1Rcf0BjfNuseY
title: Windows Subsystem for Linux
desc: ''
updated: 1639879547900
created: 1639707317036
---
# Windows Subsystem for Linux (WSL)
ref: 
- [Microsoft | Docs](https://docs.microsoft.com/en-us/windows/wsl/about), 
- [Microsoft | Community](https://answers.microsoft.com/en-us/insider/forum/all/how-to-enable-the-windows-subsystem-for-linux/16e8f2e8-4a6a-4325-a89a-fd28c7841775), 
- [Appuals](https://appuals.com/how-to-fix-the-wsl-optional-component-is-not-enabled-please-enable-it-and-try-again-error-on-ubuntu/), 
- [Microsoft | Docs | Manual installation WSL](https://docs.microsoft.com/en-us/windows/wsl/install-manual),
- [Microsoft | Docs | WSL VS Code](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode),
- [Microsoft | Docs | set up WSL development environment](https://docs.microsoft.com/en-us/windows/wsl/setup/environment)

The Windows Subsystem for Linux lets developers run a GNU/Linux environment -- including most command-line tools, utilities, and applications -- directly on Windows, unmodified, without the overhead of a traditional virtual machine or dualboot setup.

Step-by-step to install WSL2 on Win 10 machine:

1. Enable Developer Mode in Windows 10
    ![dev-mode](https://filestore.community.support.microsoft.com/api/images/7bc30f2d-4c28-45c5-9b89-d13caf6f5a69){max-width: 300px, display: block, margin: 0 auto}
2. Enable `Windows Subsystem for Linux` and `Virtual Machine Platform`
    ![windows-features-on](https://i.imgur.com/WLSaIqc.jpg){max-width: 300px, display: block, margin: 0 auto}
    If it doesn't work, enable them through PowerShell (with administrative privileges)
    ```powershell
    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
    ```
    ```powershell
    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
    ```
3. Set WSL 2 as my default version
    ```powershell
    wsl --set-default-version 2
    ```
4. Open up the `Microsoft Store` and search for `WSL` to install a Linux Distribution. 
    ![wsl-microsoft-store](https://docs.microsoft.com/en-us/windows/wsl/media/store.png){max-width: 300px, display: block, margin: 0 auto}
    I chose `Ubunto 20.04 LTS`
5. Check result  
    ```powershell
    wsl -l -v
    ```
    ![result-example](https://adamtheautomator.com/wp-content/uploads/2019/09/revert-linux-distro-wsl.png)
    The version shows `2`. And distro name shows `Ubuntu-20.04` is OK.
6. Install VS Code and the Remote WSL extension
    - Install Visual Studio Code on Windows (not in your WSL file system)
    - When prompted to Select Additional Tasks during installation, be sure to check the Add to PATH option so you can easily open a folder in WSL using the code command
    - Install the [Remote-WSL extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl)

## Working across Windows and Linux file systems
ref: [Microsoft | Docs](https://docs.microsoft.com/en-us/windows/wsl/filesystems)

We recommend against working across operating systems with your files, unless you have a specific reason for doing so. For the fastest performance speed, store your files in the WSL file system if you are working in a Linux command line (Ubuntu, OpenSUSE, etc). If you're working in a Windows command line (PowerShell, Command Prompt), store your files in the Windows file system.

For example, when storing your WSL project files:
- Use the Linux file system root directory: `\\wsl$\Ubuntu-18.04\home\<user name>\Project`
- Not the Windows file system root directory: `/mnt/c/Users/<user name>/Project$ or C:\Users\<user name>\Project`

You can view the directory where your files are stored by opening the Windows File Explorer from the command line, using:
```bash
explorer.exe .
```
> Notice the dot (`.`) at the end of command, to mark the current folder to be opened.

To view all of your available Linux distributions and their root file systems in Windows File explorer, in the address bar enter: `\\wsl$`
![linux-file-explorer](https://docs.microsoft.com/en-us/windows/wsl/media/windows-file-explorer.png){max-width: 300px, display: block, margin: 0 auto}