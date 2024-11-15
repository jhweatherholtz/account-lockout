<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>





Configuring an account lockout policy in Active Directory using Group Policy involves defining settings that control when an account is locked after multiple failed login attempts, how long the account remains locked, and how the lockout counter is reset. Here’s a step-by-step guide on how to do this:

![Screenshot 2024-11-14 201315](https://github.com/user-attachments/assets/f436edb4-69d3-4581-bc76-aedb5a8d1757)


1. Open the Group Policy Management Console (GPMC)
Log in to a machine with Group Policy Management Console installed (typically, a Domain Controller).
Click Start, and type gpmc.msc in the search box, then press Enter. This opens the Group Policy Management Console.

![Screenshot 2024-11-14 201447](https://github.com/user-attachments/assets/acb5e7b6-b2d9-428d-964b-9c135c313351)


2. Create or Edit a Group Policy Object (GPO)
In the GPMC, navigate to the Group Policy Objects section.
Right-click Group Policy Objects and select New to create a new GPO, or right-click an existing GPO and select Edit to modify it.
Give the new GPO a descriptive name if you're creating a new one, like "Account Lockout Policy".

![Screenshot 2024-11-14 201704](https://github.com/user-attachments/assets/0b9cbfa2-e8ca-4e9b-8f25-057ad6c02c71)


3. Navigate to the Account Lockout Policy Settings
In the Group Policy Management Editor, expand the following:
Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Account Lockout Policy.

![Screenshot 2024-11-14 202029](https://github.com/user-attachments/assets/e3a6b061-ce47-4544-9e1b-7e7adaa5b453)


4. Configure Account Lockout Policy Settings
You will see three primary settings that you need to configure:
Account Lockout Duration:
Definition: The time in minutes that an account remains locked before it is automatically unlocked.
Configuration: Double-click on this setting, select Define this policy setting, and then set the duration (e.g., 30 minutes).
Account Lockout Threshold:
Definition: The number of failed logon attempts that will trigger an account lockout.
Configuration: Double-click on this setting, select Define this policy setting, and then set the threshold (e.g., 3 invalid attempts).
Reset Account Lockout Counter After:
Definition: The time in minutes after which the failed logon attempts counter is reset to 0, assuming there are no additional failed logon attempts.
Configuration: Double-click on this setting, select Define this policy setting, and then set the time (e.g., 15 minutes).


LOG INTO CLIENT-1 AS JANE ADMIN mydomain.com\jane_admin:

![Screenshot 2024-11-14 202446](https://github.com/user-attachments/assets/4cdd2ba1-b73d-4ce5-b250-d0a8c45cf6fe)


5. Update Group Policy
You can wait for the Group Policy to propagate automatically, or you can force an update immediately.
On a client machine or server, open Command Prompt and type gpupdate /force, then press Enter.

![Screenshot 2024-11-14 202655](https://github.com/user-attachments/assets/75783bff-7f9c-4e8a-afd3-77d92e6c4c47)


6. Verify the Policy was updated by typing in administrator Command Line gpresult /r

RETURN TO ACTIVE DIRECTORY PAGE TO CONTINUE: [ACTIVE DIRECTORY](https://github.com/jhweatherholtz/configure-ad)


