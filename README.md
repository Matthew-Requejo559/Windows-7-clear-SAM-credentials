# Windows-7-clear-SAM-credentials

### The other day my friends mom asked me to set up a "new" laptop she had purchased from one of our acquaintances. The computer was an old Toshiba Satellite running Windows 7 with an account named Karma on it. My friend said our acquaintance had given her the log on information so everything should be fine. Unfortunately, when I brought the laptop home to set up, the log on information was incorrect. My first instinct was to put the laptop in recovery mode and just wipe it clean since my frineds mom did not need any of the files on it. But since it was Windows 7, I decided to have a little fun with it and try and bypass the password. 

### The login information in Windows is stored in the SAM registry file. From Windows, you can see this file in System32\config, but as a Windows user you cannot read the file, or look at its contents in REGEDIT. I was going to access the file system from Linux, copy it, use chntpw in linux to clear the credentials, and then copy the new SAM file back into Windows, boot up, and login to the account. 

![20230917_145952](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/91002ca7-e951-4ffe-ba09-eb5464ca7bea)

