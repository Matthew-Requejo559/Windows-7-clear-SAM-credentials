# Windows-7-clear-SAM-credentials

### OS used: 
* ### Linux (various)
* ### Windows 7
### Program used:
* ### chntpw
### Goal:
* ### clear the password for user: Karma

#### The other day my friends mom asked me to set up a "new" laptop she had purchased from one of our acquaintances. The computer was an old Toshiba Satellite running Windows 7 with an account named Karma on it. My friend said our acquaintance had given her the log on information so everything should be fine. Unfortunately, when I brought the laptop home to set up, the log on information was incorrect. My first instinct was to put the laptop in recovery mode and just wipe it clean since my frineds mom did not need any of the files on it. But since it was Windows 7, I decided to have a little fun with it and try and bypass the password. I had done a lab in school where we dumped the hashes from the SAM file. Now i wanted to try something similar in real life.

#### The login information in Windows is stored in the SAM registry file. From Windows, you can see this file in System32\config, but as a Windows user you cannot read the file, or look at its contents in REGEDIT. I was going to access the file system from Linux, copy it, use chntpw in linux to clear the credentials, and then copy the new SAM file back into Windows, boot up, and login to the account. 

#### This is what i was met with when i tried to log in with the password they gave me of Bre6969

![20230917_145952](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/91002ca7-e951-4ffe-ba09-eb5464ca7bea)

![20230917_150007](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/c6811728-87f0-402c-afaf-09741c61c6b7)


#### So, i booted into Linux from a thumb drive so i can copy over the SAM file to another thumb drive. I used Ubuntu Studio for this first part only becuase what i thought was Kali Live was actually a blank thumb drive that i had reformatted a while back. Ubuntu Studio takes forever to actually boot, but any Linux distro would have worked. At the end of this process i found a Parrot OS thumb drive and used that to complete the process. 

#### Accessing the file from Linux:

![20230911_204128](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/671172d1-3f1c-4ff8-bad4-1472898ff534)

![20230911_204144](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/bed462b4-0296-4eff-a945-795ebf99630d)

![20230911_204153](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/c1187519-c2a1-4cf8-85c9-92c79a698ded)

![20230911_204210](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/a60dbc2e-8086-4f04-a938-9892f5f3346d)

![20230911_204218](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/ff33f119-5891-4b26-9424-ad9fa71ddc1e)

![20230911_204239](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/4754364e-b0f9-4e1b-a796-6f797b2f09fd)

#### me copying it to the desktop of Ubuntu Studio
![20230911_204301](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/22aea815-f2f1-4a26-bf30-6bfba28f557f)

#### me copying it to a separate 2gb thumb drive so i can edit it later.
![20230911_204644](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/0c8923a8-7713-4005-80bd-31550576089e)

#### i also grabbed some other files just in case i needed them. Turns out these were useless. I should have grabbed the SYSTEM file with the SAM file. Oh well, i'll grab it later.
![20230911_204626](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/31834d32-f7f1-49c4-93fd-7b0bb7e82dd7)

#### i then unmounted and booted into my regular Ubuntu desktop computer so i could download the CHNTPW program. 

![01](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/2a255e19-5a42-4c7d-9fdb-3f20de08a112)








