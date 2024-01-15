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
