<h1 align='center'> Active Directory: Home Lab</h1>
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>




<p>Welcome to the "Active Directory: Home Lab" project, where we will carry out various hands-on activities to improve our understanding of user provisioning and administration within Active Directory.</p>

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
<strong>Objective:</strong> Organize the directory

- From Server Manager, click on "Tools" -> Active Directory Users and Computers

- Right-click the domain name and select "New" -> Organizational Unit. We will create an OU called "domain.com"
  
- Inside the "domain.com" OU, create nested OUs. Eg., Domain Computers, Domain Users, Domain Groups.

  
  ![image](https://github.com/user-attachments/assets/e1421bb9-3b44-4922-9fa0-40f0465ae6ff)
<br>
<br>


<h3>&#9313; Creating User Accounts</h3>
<strong>Objective:</strong> Create user accounts with specific attributes

- Navigate to the "Domain Users" OU, right-click, and select "New" -> User


  ![image](https://github.com/user-attachments/assets/b05dc567-2ba2-4a17-939f-27153baec336)
- Fill in the user details: First Name, Last Name, User Logon Name

- Set a password and configure the account settings

- You can create more users following the steps above

  ![image](https://github.com/user-attachments/assets/1bc666ab-0460-44ff-84db-a357a2f7c28f)
<br>
<br>

<h3>&#9314; Creating Groups</h3>

<strong>Objective:</strong>  Create security and distribution groups


- Navigate to the "Domain Groups" OU, right-click the OU, and select "New" -> Group.
- Name the group, Eg., Sales Department, and select the group scope  and group type 

![image](https://github.com/user-attachments/assets/c3b6e465-2064-4a4d-b748-5771d49f119f)

![image](https://github.com/user-attachments/assets/e78a2525-1520-4694-9cdf-27199350856c)

<br>
<br>


<h3>&#9315; Adding Users to Group</h3>
<strong>Objective:</strong>  Group membership management


- Double-click on a group to open the properties window
-  Go to the "Members" tab and click on "Add"
- Enter the name of a user and click "Check Names". Click on "Apply" and "Ok" to apply changes

  ![image](https://github.com/user-attachments/assets/4fdf7dc8-04e4-4ef0-9082-b063ca14d37d)

- Verify the membership in the "Members" tab of the group

  ![image](https://github.com/user-attachments/assets/1f768c3e-1f12-4ee5-9863-3e85b36a04dd)

- Do the same for other users you want to add to groups
<br>
<br>

<h3>&#9316; Configuring File Sharing and Permissions for Users</h3>
<strong>Objective:</strong>   Set up file sharing within the AD environment


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
<br>
<br>

<h3>&#9317; Configuring File Sharing and Permissions for Groups</h3>

- From the Server Manager, select "File and Storage Services" -> Shares -> right-click a space and select "New Share" 


![image](https://github.com/user-attachments/assets/a572cf94-358f-4e0b-9a6c-404b5daaea61)

- Select SMB Share-Quick -> Select a volume -> Enter a name and a description for the Share -> Configure the Share settings -> Customize Share permissions(this is where you add the group you are creating the file share for), and follow the prompt to create the share

![image](https://github.com/user-attachments/assets/3bb4bd92-cbbf-485f-9d98-dc8267a597c0)

- Follow the same steps to create a file share for other groups
  
  ![image](https://github.com/user-attachments/assets/e79c4101-bbf9-420d-8e1d-23787465214b)

- Verify by logging into a client PC as a member of one group and try accessing the file share. Members should only be able to access the folders assigned to their group.
<br>
<br>

<h3>&#9317; Map Network Drives via Group Policy</h3>
Creating a shared folder

- In the "Active Directory Users and Computers" window, right-click on a domain or OU -> New -> Shared Folder
- In the pop-up window, enter the name and network path of the shared folder

![image](https://github.com/user-attachments/assets/ac155640-e5d3-4730-99b8-a41ca116dc6a)

Creating and linking the GPO

- Inside "Group Policy Management", right-click a domain or OU and select "Create a GPO in this domain, and Link it
here".
- Name the GPO. Let's call our GPO "HR Mapped Drive"
- Right the GPO and select "Edit" -> User Configuration -> Preferences -> Windows Settings -> right-click "Drive Maps" -> New -> Mapped Drive

  ![image](https://github.com/user-attachments/assets/e9ad6d1e-556b-4813-a818-ff68d630b785)
- From the popup window, select browse(three dots beside the location box), select the shared folder we created in the steps above, and click ok
- In the next window, select a drive letter and check the "Reconnect" box
- Click "Apply" and "OK"
    
![image](https://github.com/user-attachments/assets/d767caf9-841b-4cc6-a323-b393adc97219)

Security filtering and delegation
- In the "Security Filtering" pane, remove "Authenticated Users" and add the specific group, in this case, HR Department
  
  ![image](https://github.com/user-attachments/assets/fcf00767-565e-4f8d-bbd8-a1ff77a341b4)
- You can add the "Authenticated Users" and grant them "Read" permission in the "Delegation" tab
- Log into one of the client PCs as a member of the HR Department and run the command "gpupdate /force" at the command prompt.
- Confirm from File Explorer that the drive has been successfully mapped
  
    ![image](https://github.com/user-attachments/assets/4a9db0d8-a0ff-4e1f-b778-6a5eac821ec7)
  <br>
  <br>

  
<h3>&#9318; Creating and Linking Group Policy Objects(GPOs)</h3>
<strong>Objective:</strong> Create and link policies to OUs.



<strong>Before performing this task, here are a few things to note: </strong>

<strong>I. Make sure the software installer file is in a shared folder and accessible from the client PCs</strong>

<strong>II. Move the client PCs from the Computers container to the "Domain Computers" OU you created</strong>
<br>

Creating and linking the GPO

- From the Server Manager, click "Tools", and open the "Group Policy Management" console.
- Right-click the domain or an OU, select "Create a GPO in this domain, and Link it
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
- Restart your PC so the changes take effect.
- Now every computer under the "domain.com" domain should have 7Zip installed
