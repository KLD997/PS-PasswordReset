# PS-PasswordReset
TL:DR - PowerShell script for resetting passwords, written for a clients specific password requirements.

This script was created for the purpose of assisting Tier 1 Agents in resetting user passwords for a specific client.
This client created user passwords based off three parameters specific to the user.
This client had 200+ sites across the continential USA and CA, USer info was stored in subdirectories specific to location.
These passwords were stored locally in AD as extensionAttributes.

Steps to reset password without script:

1. Open Active Directory Users & Computers
2. Select "View" in top navigation bar, and checkmark "Advanced Options"
3. Navigate to the search field and search for user (john doe)
4. Open users Properties and click "Object"
5. Make note of user object, then scale the AD tree to location. 
Ex. CompanyA > 
             Users > 
                     Employees > 
                                 Sites > 
                                         OHA > 
                                               Users > 

6. Open user Properties
7. Open "Attribute Editor"
8. Find user password inside extensionAttributes
9. Copy user password from extensionAttribute field
10. Reset user password
11. Select "User cannot change password"
12. Select "User password does not expire"
13. Notify user that password has been reset and to allow 30 minutes for changes to take effect.

Steps required with script

1. Launch PS-PasswordReset.ps1 on desktop
2. Enter user name using company standard (firstName.lastName)
3. Notify user that password has been reset and to allow 30 minutes for changes to take effect.



For Tier 1 Agent unfamiliar with AD, this cut passwsord reset times down from 8-13 minutes to 1-2 minutes! (A 700% decrease from 14 minutes to 2 minutes)
This time percentage does not account for the time saved training new Agents, which also was drastically lowered.
