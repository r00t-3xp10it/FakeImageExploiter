[![Version](https://img.shields.io/badge/FakeImageExploiter-1.3-brightgreen.svg?maxAge=259200)]()
[![Stage](https://img.shields.io/badge/Release-Stable-brightgreen.svg)]()
[![Build](https://img.shields.io/badge/Supported_OS-kali,Ubuntu,Mint,Parrot-blue.svg)]()


![FakeImageExploiter v1.4](http://i.cubeupload.com/9syjVi.png)


## FakeImageExploiter v1.4 - backdoor images.jpg[.ps1]
    CodeName: Metamorphosis
    Version release: v1.4 (Stable)
    Author: pedro ubuntu [ r00t-3xp10it ]
    Distros Supported : Linux Ubuntu, Kali, Mint, Parrot OS
    Suspicious-Shell-Activity (SSA) RedTeam develop @2017

## Legal Disclamer:
    The author does not hold any responsibility for the bad use of this tool,
    remember that attacking targets without prior consent is illegal and punished by law.

<br /><br />

## Description:
    This module takes one existing image.jpg and one payload.ps1 (input by user) and
    builds a new payload (agent.jpg.exe) that if executed it will trigger the download of
    the 2 previous files stored into apache2 (image.jpg + payload.ps1) and execute them.

    This module also changes the agent.exe Icon to match one file.jpg Then uses the spoof
    'Hide extensions for known file types' method to hidde the agent.exe extension.

    All payloads (user input) will be downloaded from our apache2 webserver
    and executed into target RAM. The only extension (payload input by user)
    that requires to write payload to disk are .exe binaries.
 
## Exploitation:
    FakeImageExploiter stores all files in apache2 webroot, zips (.zip) the agent,
    starts apache2 and metasploit services(handler), and provides a URL to send to
    target (triggers agent.zip download). As soon as the victim runs our executable,
    our picture will be downloaded and opened in the default picture viewer, our
    malicious payload will be executed, and we will get a meterpreter session.

    But it also stores the agent (not ziped) into FakeImageExploiter/output folder
    if we wish to deliver agent.jpg.exe using another diferent attack vector.

    'This tool also builds a cleaner.rc file to delete payloads left in target'
![FakeImageExploiter v1.4](http://i.cubeupload.com/sbGXRv.png)

## Payloads accepted (user input):
    payload.ps1 (default) | payload.bat | payload.txt | payload.exe [Metasploit]
    "Edit 'settings' file before runing tool to use other extensions"
![FakeImageExploiter v1.4](http://i.cubeupload.com/EOAi8P.png)

## Pictures accepted (user input):
    All pictures with .jpg (default) | .jpeg | .png  extensions (all sizes)
    "Edit 'settings' file before runing tool to use other extensions"
![FakeImageExploiter v1.4](http://i.cubeupload.com/WfcNbW.png)

<br /><br />

## Dependencies/Limitations:
    xterm, zenity, apache2, mingw32[64], ResourceHacker(wine)
    'Auto-Installs ResourceHacker.exe under ../.wine/Program Files/.. directorys'

    WARNING: To change icon manually (resource hacker bypass) edit 'settings' file.
    WARNING: Only under windows systems the 2º extension will be hidden (so zip it) 
    WARNING: The agent.jpg.exe requires the inputed files to be in apache2 (local lan hack)
    WARNING: The agent.jpg.exe uses the powershell interpreter (does not work againts wine).
    WARNING: This tool will not accept payload (user input) arguments (eg nc.exe -lvp 127.0.0.1 555)
    WARNING: The ResourceHacker provided by this tool requires WINE to be set to windows 7
![FakeImageExploiter v1.4](http://i.cubeupload.com/AxScDp.png)

<br /><br />

## Another senarios:
    If you wish to use your own binary (user input - not metasploit payloads) then:
1º - Edit 'settings' file before runing tool and select 'NON_MSF_PAYLOADS=YES'
![FakeImageExploiter v1.4](http://i.cubeupload.com/dSO7aG.png)
2º - Select the binary extension to use
![FakeImageExploiter v1.4](http://i.cubeupload.com/EOAi8P.png)
**'Remmenber to save settings file before continue'** ..

3º - Run FakeImageExploiter to metamorphosis your binary (auto-storage all files in apache) ..
![FakeImageExploiter v1.4](http://i.cubeupload.com/lBxRtJ.png)
4º - Open new terminal and execute your binary handler to recibe connection.
**HINT: This funtion will NOT build a cleaner.rc**

<br /><br />

## The noob friendly funtion:
    Bypass the need to input your payload.ps1, And let FakeImageExploiter take
    care of building the required payload.ps1 + agent.jpg.exe and config the handler.
    "With this funtion active, you only need to input your picture.jpg :D"
![FakeImageExploiter v1.4](http://i.cubeupload.com/BCpMDr.png)
    Select the binary extension to use
![FakeImageExploiter v1.4](http://i.cubeupload.com/EOAi8P.png)
**HINT: This funtion allow users to build (ps1|bat|txt) payloads**<br />
**HINT: This funtion will NOT build .exe binaries**

<br /><br />

## "WINE is not owned by you":
    If you get this message it means that you are executing FakeImageExploiter
    as sudo and your wine installation belongs to user (is not owned by you) to
    bypass this issue just execute FakeImageExploiter as the wine owner.
    EXAMPLE: If wine its owned by spirited_wolf, execute tool without sudo
    EXAMPLE: If wine its owned by root, execute tool as sudo

<br /><br />

## Download/Install/Config:
    1º - Download framework from github
         git clone https://github.com/r00t-3xp10it/FakeImageExploiter.git

    2º - Set files execution permitions
         cd FakeImageExploiter
         sudo chmod +x *.sh

    3º - Config FakeImageExploiter settings
         nano settings

    4º - Run main tool
         sudo ./FakeImageExploiter.sh

<br /><br />

## Framework Banner
![FakeImageExploiter v1.4](http://i.cubeupload.com/9syjVi.png)
## settings file
![FakeImageExploiter v1.4](http://i.cubeupload.com/mEXNBS.png)
## Agent(s) in windows systems
![FakeImageExploiter v1.4](http://i.cubeupload.com/3bniTw.jpg)

<br />

## Video tutorials:
FakeImageExploiter [ Official release - Main funtions ]: https://www.youtube.com/watch?v=4dEYIO-xBHU

FakeImageExploiter [ the noob friendly funtion ]: https://www.youtube.com/watch?v=abhIp-SG4kM

FakeImageExploiter [ bat payload - worddoc.docx agent ]: https://www.youtube.com/watch?v=Ah4hejGhj-M

FakeImageExploiter [ txt payload - msfdb rebuild ]: https://www.youtube.com/watch?v=g2E73GyxKhw

<br />

### Special thanks:
**@nullbyte** | **@Yoel_Macualo** | **@0xyg3n** (SSA team menber)

Credits: https://null-byte.wonderhowto.com/how-to/hide-virus-inside-fake-picture-0168183

**Suspicious-Shell-Activity (SSA) RedTeam develop @2017**
