<h1 align='center'> Active Directory: Home Lab</h1>
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>




<p>Welcome to the "Active Directory: Home Lab" project, where we will simulate scenarios to improve our understanding of user provisioning and administration within Active Directory..</p>

<h2>Prerequisites</h2>

- <a href="https://github.com/a-rashid-saaka/Azure-VM-deployment"> Azure VM Setup and Network Configuration </a>
- <a href="https://github.com/a-rashid-saaka/Active-Directory-installation"> Active Directory Deployment and Setup </a>
- <a href="https://github.com/a-rashid-saaka/Active-Directory-user-creation">Active Directory Bulk User Account Creation </a>
<h2> Objectives</h2>

<h4>Scenario Simulation</h4>

- Participate in practical simulations of various scenarios, such as file sharing and creating Group Policy Objects (GPOs).

<h4>Troubleshooting Scenarios</h4>

- Enhance troubleshooting skills by simulating user access issues and learning to resolve them effectively.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Active Directory Domain Services
- Command Prompt

<h2>Operating Systems Used </h2>

- Windows (Windows Server 2019 Datacenter)
- Windows (Windows 10 Pro)

  <h1>Scenarios</h1>

<h3>&#9312; Creating Organizational Units(OUs) </h3>
Objective: Organize the directory

- From Server Manager, click on "Tools" -> Active Directory Users and Computers

- Right-click the domain name and select "New" -> Organizational Unit. We will create an OU called "domain.com"
  
- Inside the "domain.com" OU, create nested OUs. Eg., Domain Computers, Domain Users, Domain Groups.

  
  ![image](https://github.com/user-attachments/assets/e1421bb9-3b44-4922-9fa0-40f0465ae6ff)
<br>
<br>


<h3>&#9313; Creating User Accounts</h3>

- Navigate to the "Domain Users" OU, right-click, and select "New" -> User


  ![image](https://github.com/user-attachments/assets/b05dc567-2ba2-4a17-939f-27153baec336)
- Fill in the user details: First Name, Last Name, User Logon Name

- Set a password and configure the account settings

- You can create more users following the steps above

  ![image](https://github.com/user-attachments/assets/1bc666ab-0460-44ff-84db-a357a2f7c28f)
<br>
<br>

<h3>&#9314; Creating Groups</h3>


- Navigate to the "Domain Groups" OU, right-click the OU, and select "New" -> Group.
- Name the group, Eg., Sales Department, and select the group scope  and group type 

![image](https://github.com/user-attachments/assets/c3b6e465-2064-4a4d-b748-5771d49f119f)

![image](https://github.com/user-attachments/assets/e78a2525-1520-4694-9cdf-27199350856c)
<br>
<br>

<h3>&#9315; Adding Users to Group</h3>

- Double-click on a group to open the properties window
-  Go to the "Members" tab and click on "Add"
- Enter the name of a user and click "Check Names". Click on "Apply" and "Ok" to apply changes

  ![image](https://github.com/user-attachments/assets/4fdf7dc8-04e4-4ef0-9082-b063ca14d37d)

- Verify the membership in the "Members" tab of the group

  ![image](https://github.com/user-attachments/assets/1f768c3e-1f12-4ee5-9863-3e85b36a04dd)

- Do the same for other users you want to add to groups
<br>
<br>

<h3>&#9316; Configuring File Sharing and Permissions</h3>

- Create a folder named "ALL SHARES" on the C: drive.
- Right-click the folder and select "Properties."
- On the "Sharing" tab, click "Advanced Sharing."
  
  ![image](https://github.com/user-attachments/assets/a8cfc859-45e7-4070-94b8-02b4be95966b)

- Check "Share this folder" and Click "Permissions" and set the share permissions

  
  ![image](https://github.com/user-attachments/assets/a911fb01-baec-48b4-a54b-2a1e2d403969)
  
- Remove "Everyone" and add "Authenticated Users" for security.

  
  ![image](https://github.com/user-attachments/assets/5f527891-97f3-4a43-ada8-11de09f80163)
  
- In the folder properties, go to the "Security" tab.
  - Click "Edit" to modify the permissions.
  - Add the appropriate users or groups and assign the necessary permissions
    
    ![image](https://github.com/user-attachments/assets/534660b0-97fb-4976-88a7-b3770ca09b8b)
    
- Verify by logging into a client PC as an authenticated user. Then input the UNC path in File Explorer
  
  ![image](https://github.com/user-attachments/assets/da803e58-6ab7-4932-aeb3-888e6cb8c9e2)


<h3>&#9317; Creating and Linking Group Policy Objects(GPOs)</h3>
<strong>Before performing this task,make sure the software installer is in a shared folder and accessible from the client PC</strong>
<br>
- From the Server Manager, click "Tools", and open Group Policy Management Console.
- Right-click the domain or an OU, and select "Create a GPO in this domain, and Link it
here".
- Name the GPO. We will deploy the 7Zip software  so let's name our GPO "7Zip Deployment"
- Right-click on the GPO and select "Edit".
- Under "Computer Configuration", select "Policies" -> Software Settings -> Software Installation -> New -> Package
  
![image](https://github.com/user-attachments/assets/90437acb-be56-4f3c-a38b-ce8e7f86658a)

- Enter the network path of the installation file, select the file, and click "Open"

![image](https://github.com/user-attachments/assets/0f6e6132-fb6c-47d3-9cff-d8fe00eee0a0)

- Select "Assigned" and click "OK"

  ![image](https://github.com/user-attachments/assets/9f3facf2-ac3d-4482-b4d1-82a1686f377e)

  - Open the command prompt in the server PC and the client PCs in the domain, run the command "gpupdate /force" for the GPO to be applied
  - You can verify the GPO is applied correctly by running the command "gpresult /r"
- Restart your PC for the changes to take effect.
- Now every computer under the "domain.com" domain should have 7Zip installed
