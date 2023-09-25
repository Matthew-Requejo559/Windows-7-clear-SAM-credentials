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

### This is what i was met with when i tried to log in with the password they gave me of Bre6969

![20230917_145952](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/91002ca7-e951-4ffe-ba09-eb5464ca7bea)

![20230917_150007](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/c6811728-87f0-402c-afaf-09741c61c6b7)


### So, i booted into Linux from a thumb drive so i can copy over the SAM file to another thumb drive. I used Ubuntu Studio for this first part only becuase what i thought was Kali Live was actually a blank thumb drive that i had reformatted a while back. Ubuntu Studio takes forever to actually boot, but any Linux distro would have worked. At the end of this process i found a Parrot OS thumb drive and used that to complete the process. 

### Accessing the file from Linux:

![20230911_204128](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/671172d1-3f1c-4ff8-bad4-1472898ff534)

![20230911_204144](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/bed462b4-0296-4eff-a945-795ebf99630d)

![20230911_204153](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/c1187519-c2a1-4cf8-85c9-92c79a698ded)

![20230911_204210](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/a60dbc2e-8086-4f04-a938-9892f5f3346d)

![20230911_204218](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/ff33f119-5891-4b26-9424-ad9fa71ddc1e)

![20230911_204239](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/4754364e-b0f9-4e1b-a796-6f797b2f09fd)


### me copying it to the desktop of Ubuntu Studio

![20230911_204301](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/22aea815-f2f1-4a26-bf30-6bfba28f557f)


### me copying it to a separate 2gb thumb drive so i can edit it later.

![20230911_204644](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/0c8923a8-7713-4005-80bd-31550576089e)


### i also grabbed some other files just in case i needed them. Turns out these were useless. I should have grabbed the SYSTEM file with the SAM file. Oh well, i'll grab it later.

![20230911_204626](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/31834d32-f7f1-49c4-93fd-7b0bb7e82dd7)


### i then unmounted and booted into my regular Ubuntu desktop computer so i could download the CHNTPW program. 

![01](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/2a255e19-5a42-4c7d-9fdb-3f20de08a112)


### Me opening the directory in the terminal so i can edit it with CHNTPW 

![03](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/4fd8bdaa-0d05-4089-932e-8d712f39f3d6)

![04](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/5ff30593-455c-47a6-9ea7-33a928b87a9c)


### seeing how to use the program

![05](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/65beac36-fe81-4c4c-9ba4-dce30bf63db4)


### listing the users. Looks like the Karma account is seen as Amy in the registry. This can happen sometimes when people change the display name after intial account creation. No biggie. 

![07](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/500e1c3d-de46-4647-a71c-ca82a2bd980a)


### Me selecting the Amy account to edit it

![08](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/6835fef1-6777-4c7c-a876-7a5e581489c3)


### selecting 1 from edit menu to clear password

![09](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/63b1a395-0014-437d-ae3d-0c97fd592c44)


### confirmation that there is now NO hash value associated with the Amy account

![10](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/241498e0-2f00-454f-8869-3c7c12948151)


### You quit the program and save it.

### I found my Parrot OS thumb at this point and used it to boot into from the laptop.

![20230914_201805](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/d2636e56-a9ee-4bc3-a924-6f320d215388)

![20230914_202112](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/7970c829-d4a0-48cc-8c32-098d0382efca)


### from here i reversed the process from earlier and pasted the new SAM file back into System32 to replace the old one. The new one does not have a stored hash value (password) associated with the account on the laptop.

![20230914_202300](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/7b3d22a8-b0c8-47e0-b154-44bc3a0837ab)

![20230914_202319](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/400a9837-047d-4e70-ac0e-f02739dcadc6)


### first i grabbed the SYSTEM file so i can have the original SAM file along with the original SYSTEM file to try and crack the HASH later. That will be a separate tutorial. I saved them to the thumb drive in a folder called backup

![20230914_202659](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/d9420c83-1e96-42f1-a88c-ca9621aada16)


### copying the new SAM file back into Windows

![20230914_203024](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/539898f6-7ae1-46fa-b852-6fe77111ea8f)

![20230914_203038](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/d43ad850-cee5-4ba9-a543-72c9d3642ae8)

![20230914_203055](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/5311b49f-7296-4cd5-b275-07df3fa08fe2)


### shutting down to see if it all worked

![20230914_203139](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/81024bb4-b134-4f57-b2f9-deac21319c41)

### Booting into Windows

![20230914_203336](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/2ee016d9-7b22-4b15-9d7d-2344ae18c5e6)


### SUCCESS!! it auto logged in!

![20230914_203352](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/127addd8-b11c-4314-8d2d-40ea33d889d3)

![20230914_203404](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/5363738a-2ce6-4e55-b5b3-15ebc566e9d9)


### some of the original files that were on the computer from previous owner

![20230914_203837](https://github.com/Matthew-Requejo559/Windows-7-clear-SAM-credentials/assets/136190678/3dfe783b-ccea-4a17-8fb3-656bede39039)

## Next one i will use some different programs to try and crack the original HASH so i can see just how far off the password we were given was from the real password. 


