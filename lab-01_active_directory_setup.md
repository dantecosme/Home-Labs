Home lab practice using Oracle Virtualbox 

---
# Configuration
- Created new VM running the Windows Server 2022 datacenter (WinServer2022Lab).
	Allocated resources: 2 CPU cores, 4GB RAM, 60GB Storage
	Password: <SERVER_ADMIN_PASSWORD>
- Set network type to bridged
- Confirmed internet connectivity using `ipconfig` and `tracert`

- Created 2nd VM running Windows 11 enterprise(Win11).
	Allocated resources: 4 CPU cores, 10GB RAM, 100GB Storage
	Password: <WIN11_LOCAL_PASSWORD>
- Set network type to bridged
- Confirmed internet connectivity using `ipconfig` and `tracert`

- Accessed Server Manager in order to configure WinServer2022Lab as the first AD domain controller in a new forest. <LAB_DOMAIN.local>
	Directory Services Restore Mode(DSRM) password: <DSRM_PASSWORD>

- Created new admin user account named 'help desk', logon name: helpdesk@ADDS_ServerLab.local
- Accessed Win11 and set DNS IPv4 to match that of my AD Server(WinServer2022Lab)
- Successfully logged onto the admin account and added the Win11 VM to the AD domain
---
# Creating Users & Organizational Units
In the domain controller:
- Created new OU `Homelabcompany`
	- Created three more nested OUs `Users`, `Groups`, `Workstations`

- Within `Users` sub-OU, created new users. All new accounts will require their password to be changed on next login.
- User 1
	Full name: Gol D. Roger
	Username: GDRoger
	Password: <INITIAL_USER1_PASSWORD>
- User 2
	Full name: John Smith
	Username: Jsmith
	Password: <INITIAL_USER2_PASSWORD>
- User 3
	Full Name: Alice Chains
	Username: AliceC
	Password: <INITIAL_USER3_PASSWORD>

- Edited the following property fields for each user: `Description`, `Telephone Number`, `Job Title`, `Department`

- Within the `Groups` sub-OU, I created three security groups with global scope: `Help Desk Team`, `HR Team`, `IT Team`

In Win11 workstation, previously added to the domain:
- Verified that User 1's account is functional and changed password
	Username: GDRoger
	Password: <USER1_NEW_PASSWORD>
- Verified that User 2's account is functional and changed password
	Username: Jsmith
	Password: <USER2_NEW_PASSWORD>
- Verified that User 3's account is functional and changed password
	Username: AliceC
	Password: <USER3_NEW_PASSWORD>


