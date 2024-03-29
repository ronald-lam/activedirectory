<h1>Active Directory</h1>

<h2>Description</h2>
<p>
This repository is to showcase what I've learned from using Active Directory(AD). 
I will refer back to this repository sometimes to remind myself of what I've learned from using this directory service.
I'll also update this repository with new knowledge, instructions, and screenshots whenever I come across a new function in AD.
Some screenshots I provde are self-explanatory so I won't be going into depth with the instructions. I will, however, explain some
functionalities that are not evident to a new user of AD.
</p>
<p>
There are plenty of videos and tutorial on how to setup an AD homelab so I will not be going into detail on how to set it up. 
In short, this homelab was created using Oracle VM Virtualbox to host my virtual machines(VM), 
Windows 10 as the operating system for my domain controller(dc) and VMs, and Windows Server 2019
as the server for my dc. My domain name is <strong>mydomain</strong>.
</p>
<hr />
<h3>Creating a new user</h3>
<p>
  To create a new user, begin by right clicking on the domain name on the left side of the AD users and computers menu.
  Then hover over new, then user. 
</p>
<img src="https://i.imgur.com/4KY8w5r.png" height="80%" width="80%" alt="Create new user"/>
<img src="https://i.imgur.com/Gvy5mwn.png" height="80%" width="80%" alt="Input user info"/>
<img src="https://i.imgur.com/hdj9qdE.png" height="80%" width="80%" alt="Create password"/>
<p>
  <strong>*IMPORTANT*</strong> This will be a temporary password for the new employee when they first login into their company-provided laptop or desktop.
  As an admin, I should not be allowed to know the password that an employee uses to login, so by clicking on the checkbox that says "User must change password at next logon", 
  the employee will have to create their own password and should not let anyone else know what it is. 
</p>
<p>
  I can also click on the checkbox to disable user account as this will prevent unauthorized users from going into a new employees account. Only once the new employee has notified me
  via a phone call or email will I uncheck this box. Sometimes, this is a recommended action for security purposes. 
</p>
<img src="https://i.imgur.com/WAeXFZy.png" height="80%" width="80%" alt="Confirm new user"/>

<hr />
<h3>Creating a new group</h3>
<p>To create a new group, right-click and hover over new, then user.</p>
<img src="https://i.imgur.com/c6QehFN.png" height="80%" width="80%" alt="Create new group"/>
<img src="https://i.imgur.com/SYeSrkT.png" height="80%" width="80%" alt="Input group info"/>
<img src="https://i.imgur.com/GRv6anb.png" height="80%" width="80%" alt="Confirm"/>
<p>
<strong>Security Groups Type</strong>(not to be confused with the name of the group, Security) are used to manage access to resources and users added to a 
security group will inherit permissions assigned to that group.
</p>
<p>The other type of group are <strong>Distribution Groups</strong>. They are used for email distributions. When an email is sent to a distribution group, it's delivered to all members of the group. </p>
<p>The <strong>Domain Local scope</strong> provide access to resources within a specific domain. They can contain users, groups, and computers from any domain in the same forest but are used for assigning permissions within the domain where they are created. Think of these as keys to specific rooms in a house. They decide who can enter and access different rooms within the house (domain).</p>
<p>
  <strong>Global scope</strong> are used to organize and manage users and computers from the same domain. They can be members of domain local groups and can have permissions assigned within their own domain.
  Imagine these as groups of friends within the same city. They help organize and manage people within the city but don't have keys to specific rooms in the house.
</p>
<p>
  <strong>Universal scope</strong> are used to manage users and computers across different domains in a forest. They can contain members from any domain in the forest and can have permissions assigned in any domain. Universal groups are useful in multi-domain or multi-forest environments.  Picture these as VIP passes that work in multiple cities. They allow access to rooms (resources) across different houses (domains) in a larger region (forest).
</p>

<hr />
<h3>Changing a user's password</h3>
<p>Sometimes, a user may forget their password and needs to reset their password. As an admin, you can give the user a new, temporary password to login, then have them make a new password for themselves.</p>
<img src="https://i.imgur.com/MQtJ4S8.png" height="80%" width="80%" alt="Look for this icon"/>
<p>Look for this icon circled in red</p>
<img src="https://i.imgur.com/PIgKDnp.png" height="80%" width="80%" alt="Narrow the search"/>
<p>You can widen the scope of the search by selecting "Entire Directory". This will search for users all throughout your entire domain.</p>
<img src="https://i.imgur.com/tFBraUi.png" height="80%" width="80%" alt="Right-click then reset"/>
<p>Right click on a user's name, then click"Reset Password".</p>
<img src="https://i.imgur.com/RRdz4gW.png" height="80%" width="80%" alt="Reset password"/>
<p>Clicking on the change password at next logon checkbox should always be done since no one else including admins shouldn't know the users password.</p>
<img src="https://i.imgur.com/GCwDFBZ.png" height="80%" width="80%" alt="Try logging in as user"/>
<p>Let's confirm if the user can login with the new temporary password by logging in as the user.</p>
<img src="https://i.imgur.com/4bktk8i.png" height="80%" width="80%" alt="User changes password"/>
<img src="https://i.imgur.com/ekxfGti.png" height="80%" width="80%" alt="Password change confirmed"/>

<hr />
<h3>Adding/Removing a user to a group</h3>
<p>To add a user to a group, find and right-click on the name of the user you want to add.</p>
<img src="https://i.imgur.com/Y0XEEiG.png" height="80%" width="80%" alt="Find and right-click user"/>
<img src="https://i.imgur.com/7T65XPU.png" height="80%" width="80%" alt="Narrow search"/>
<p>Make sure to change the location parameter to your domain and objects parameter to group if needed.</p>
<p>Type the name of the group you want to add and then click "Check Names".</p>
<img src="https://i.imgur.com/frmWgoA.png" height="80%" width="80%" alt="Confirm popup"/>
<img src="https://i.imgur.com/sYkDbhF.png" height="80%" width="80%" alt="Check if user is added"/>
<p>You can check to see if the user is added by double-clicking on the user's name or right-clicking the name and then Properties.</p>
<img src="https://i.imgur.com/A6Kcrn6.png" height="80%" width="80%" alt="Click Member Of"/>
<p>Click on the member of tab and see if the user was added to the group you chose earlier.</p>
<img src="https://i.imgur.com/pAL1mmS.png" height="80%" width="80%" alt="Remove user"/>
<p>To remove a user from the group, select group name and then click the remove button.</p>
<img src="https://i.imgur.com/LzXK0GP.png" height="80%" width="80%" alt="Check to see if user is removed"/>
