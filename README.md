<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- Configuring Roles
- Configuring Departments
- Configuring Teams
- Allowing anyone to create Tickets
- Configuring Agents
- Configuring Users
- Configuring SLA's
- Configuring Help Topics

<h2>Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/QHxj4FL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before we dive into osTicket, we need to cleanup some files. So, in your osTicket folder (which is located in the Windows (c:) inside of the inetpub/wwwroot folders) go to your "setup" folder and delete it. Then after deleting the setup folder, go to your ost-config.php folder (which is located in your "include" folder near the bottom) and set the permissions back to view only. To do this, you right-click on ost-config, then go to properties and then click on the securities tab at the top and then it should give you two options to either "edit" or "advanced", click on "advanced". Now you should see a box in the middle that it titled "Permission entries" and written in the box should be the permissions that you allowed which was "everyone", double click your permission you made and it should take you back to where you initially made the permission. Instead of having every box checked, uncheck every box except for "read" and "read and execute" then click "ok" and "apply".
</p>
<br />

<p>
<img src="https://i.imgur.com/12jLfoF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now you would sign into osTicket using the credentials you filled in on the previous osTicket page. After filling in the credentials, you will now be redirected to the osTicket Homepage!
</p>
<br />

<p>
<img src="https://i.imgur.com/soBK4Hy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first thing we need to configure in osTicket are the roles. In order to get there, you need to get into the admin panel first. In order to get to the admin panel, there should be a prompt that reads "Admin panel" right next to where it says "welcome". Now you would click on the admin panel and you should see some tabs that read "Dashboard", "Settings", "Manage", "Emails", "Agents". With your cursor, hover over the "Agents" panel and you should see "roles" which should be the third option down. After clicking on roles, click on "Add new role" then when adding your first role, make a role that has control over everything. This role can be named whatever you would like but for now, we will call this role "Supreme Admin". There should be two tabs right below the "Add new role" prompt when you're deciding on the name for your role. Those two tabs should read "Definition" and "Permissions". You just filled out the definition tab with the name you chose for the role that has control over everything now you need to edit the permissions. In order for the role you made to have control over everything, you need to check every single box in the permissions tab. You should also see three new tabs that read "Tickets" "Tasks" and "Knowlegdebase". We already checked every box in "Tickets" so now make sure that every box is checked in the "Tasks" and "Knowlegdebase" tabs and after you finish doing that, click on the "Add role" at the bottom of the page.
</p>
<br />

<p>
<img src="https://i.imgur.com/62HuNlH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, we need to configure the "departments". The steps to get to departments are similar to what we did to get to "roles". So we would go to the Admin panel and go to the "Agents" tab but instead of selecting roles, we are going to select "Departments" which should be all the way at the bottom. So now we would select "add new department" and it should take us to a screen where we enter the department name. You can name the department anything you would like but for now, I will name my Department "System Administrators". After you finish naming your department, scroll to the bottom and click "Create Dept".
</p>
<br />

<p>
<img src="https://i.imgur.com/qYZKZLO.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After configuring the Roles and Departments, we need to configure the teams. Just like with both roles and departments, in order for us to configure teams we need to be in the admin panel and then go to the Agents tab and Teams should be the second option from the top. Now we select "Add new Team" and it should take us to a page where we name our team. Again, the team can be named anything you would like, but for now, I will use the name "Level II support". After you finish creating your name for your team, click on "create team"
</p>
<br />

<p>
<img src="https://i.imgur.com/3fZOXwp.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now we have to configure the agents. So in the admin panel, go to the agents tab, and you should see "agents"click on that then you should see the name that you used for osTicket there already after observing this, click on "Create new Agent". When creating a new agent, you can use any name that you would like, I will use the name "Justin Smith" then for the email, I'll use "Justinsmith@helpdesk.com". Lastly for the username I will be using "justin.smith". After filling in all those credentials for your first agent, click on "set password" then when you get to the next screen, uncheck the boxes at the top and bottom and set a password for the user you just created and then click "set". After creating your Agent and setting the password for that agent, we need to configure how much authority this agent has. So after setting the password for the agent, it should take you back to the page where you typed in your agents' credentials, so, right above where you typed your agents name, you should see some tabs titled "Account", "Access", "Permissions", "Teams". We already finished the "Account" tab so now we need to determine what your agent can access. Lets enable access to everything for our first agent. Expand "Department" and click on the department we made earlier "System Administrators" then next expand "role" and click on the role we made earlier "Supreme Admin". Then below where it says "extended access", Expand "select department" and click on "support". We don't need to worry about permissions because everything is already checked. Now for teams, expand the "select team" and click on the team we made earlier "Level II support". now we finished our first agent. After you are finished, click on "create" at the bottom. Now when you click on the agents tab again you should see your new agent. Now try to make a second agent doing everything you did for the first agent except instead of giving this access to everything, make this agents' access "view only" so in the "access" tab expand "departments" and select "support" then expand "roles" and select "view only" next for permissions, uncheck every box in "users" "organizations" and "knowlegdebase" then lastly, make this agent part of the "Level II Support" team you made.
</p>
<br />

<p>
<img src="https://i.imgur.com/2jwHR14.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next we are going to configure our "users" or "customers". So far we've done everything in the "Admin Panel" but in order to add new users, we need to go to the agent panel. So, just like how we initially accessed our admin panel, we need to do the same to access the agent panel. Where you see "welcome" then your name next to it, well, right next to that is that panel that you are not currently on, so if it says "Agent panel" then you are on the "Admin Panel" and vice-versa. Now, once you are on the Agent Panel, Click on the "Users" tab Then go to "Add User" then type in any random email or name you can think of. I used KenKen@user.com and the random name i used is Ken Ken. After filling in those Credentials, Click on "Add user" at the bottom right hand side. Next, create another random user following the steps that you just did.
</p>
<br />

<p>
<img src="https://i.imgur.com/WgZqJ2g.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now we finally are going to set our SLA's for our tickets. So currently we are in the agent panel, go inside the admin panel then in the "manage" tab go down to SLA Then click on where it says "add new SLA plan". We're going to add 3 SLA's. The first SLA plan We're going to add is called a "SEV-A". Where it says "Grace Period" type in 1 which stands for 1-hour and lastly where it says schedule, expand it and click on the "24-7" option. Next Create another new SLA plan Called a "SEV-B". Where it says "Grace Period" type in 4 which is 4-hours and where it says schedule, expand it to click on the "24-7" option. Create your last SLA plan called a "SEV-C". Where it says "Grace Period" type in 8 which is 8-hours and where it says schedule, expand it and click on the last option that says "Monday-Friday 8am-5pm with U.S. Holidays" this means that you only work on a SEV-C ticket during business days.
</p>
<br />

<p>
<img src="https://i.imgur.com/R4gN71t.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now we are going to configure the help topics. To do this, we need to head back to the admin panel and go to "manage" and one of the options should say "Help topics". After clicking on "Help Topics", go to "Add new Help Topic" after doing this, there are 4 help topics we are going to add and they are "Business Critical Outage", "Personal Computer Issues", "Equipment Request", and "Password Reset". Enter them one at a time into the Topic bar you should see after clicking on "Add new Help Topic" and after finishing each one, click on "Add topic" which should be at the bottom. With this we should be ready to do an exercise where we create our own tickets, assign the ticket to one of our agents, and determine whether the ticket is a Sev-A, Sev-B, or Sev-C
