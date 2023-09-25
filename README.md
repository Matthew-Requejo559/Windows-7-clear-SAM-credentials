# Windows-7-clear-SAM-credentials

### OS used: 
* ### Linux (various)
* ### Windows 7
### Program used:
* ### chntpw
### Goal:
* ### clear the password for user: Karma

#### The other day my friends mom asked me to set up a "new" laptop she had purchased from one of our acquaintances. The computer was an old Toshiba Satellite running Windows 7 with an account named Karma on it. My friend said our acquaintance had given her the log on information so everything should be fine. Unfortunately, when I brought the laptop home to set up, the log on information was incorrect. My first instinct was to put the laptop in recovery mode and just wipe it clean since my frineds mom did not need any of the files on it. But since it was Windows 7, I decided to have a little fun with it and try and bypass the password. 

#### The login information in Windows is stored in the SAM registry file. From Windows, you can see this file in System32\config, but as a Windows user you cannot read the file, or look at its contents in REGEDIT. I was going to access the file system from Linux, copy it, use chntpw in linux to clear the credentials, and then copy the new SAM file back into Windows, boot up, and login to the account. 

#### This is what i was met with when i tried to log in with the password they gave me of Bre6969

![20230917_145952](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/91002ca7-e951-4ffe-ba09-eb5464ca7bea)

![20230917_150007](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/c6811728-87f0-402c-afaf-09741c61c6b7)


#### So, i booted into Linux from a thumb drive so i can copy over the SAM file to another thumb drive. I used Ubuntu Studio for this first part only becuase what i thought was Kali Live was actually a blank thumb drive that i had reformatted a while back. Ubuntu Studio takes forever to actually boot, but any Linux distro would have worked. At the end of this process i found a Parrot OS thumb drive and used that to complete the process. 


