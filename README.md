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

<h3>&#9315; Adding Users to Group</h3>

- Double-click on a group to open the properties window
-  Go to the "Members" tab and click on "Add"
- Enter the name of a user and click "Check Names". Click on "Apply" and "Ok" to apply changes

  ![image](https://github.com/user-attachments/assets/4fdf7dc8-04e4-4ef0-9082-b063ca14d37d)

- Verify the membership in the "Members" tab of the group

  ![image](https://github.com/user-attachments/assets/1f768c3e-1f12-4ee5-9863-3e85b36a04dd)

- Do the same for other users you want to add to groups



  


