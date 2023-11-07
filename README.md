<h1>File permissions in Linux</h1>
<h2>Description</h2>
The research team at my organization needs to update the file permissions for certain files and directories within the projects directory. The permissions do not currently reflect the level of authorization that should be given. Checking and updating these permissions will help keep their system secure. 
<br/>
<br />

<h2>Languages and Utilities Used</h2>

- <b>Linux</b> 

<h2>Environments Used </h2>

- <b>Oracle VM (Kali LInux)</b>

<h3>Check file and directory details:</h3>

<p align="left">
The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system. 
<br/>
<img src="https://i.imgur.com/Zyd8Ffb.png" height="60%" width="60%" alt="Linux Screenshot"/>
<br />
The first line of the screenshot displays the command I entered, and the other lines display the output. The code lists all contents of the projects directory. I used the ls command with the -la option to display a detailed listing of the file contents that also returned hidden files. The output of my command indicates that there is one directory named drafts, one hidden file named .project_x.txt, and five other project files. The 10-character string in the first column represents the permissions set on each file or directory. 
<br />

<h3>Change file permissions</h3>

The organization determined that other shouldn't have write access to any of their files. To comply with this, I referred to the file permissions that I previously returned. I determined project_k.txt must have the write access removed for other. 
The following code demonstrates how I used Linux commands to do this: 
<br/>
<img src="https://i.imgur.com/8d1cypS.png" height="60%" width="60%" alt="File permissions snapshot"/>
<br />

The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The chmod command changes the permissions on files and directories. The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. In this example, I removed write 
permissions from other for the project_k.txt file. After this, I used ls -la to review the updates I made. 
<br />

<h3>Change file permissions on a hidden file </h3>

The research team at my organization recently archived project_x.txt. They do not want anyone to have write access to this project, but the user and group should have read access. 
The following code demonstrates how I used Linux commands to change the permissions: 
<br/>
<img src="https://i.imgur.com/t1KEf36.png" height="60%" width="60%" alt="Hidden files snapshot"/>
<br />
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I know .project_x.txt is a hidden file because it starts with a period (.). In this example, I removed write permissions from the user and group, and added read permissions to the group. I removed write permissions from the user with u-w. Then, I removed write permissions from the group with g-w, and added read permissions to the group with g+r. 
<br />

<h3>Change Directory Permissions </h3>

My organization only wants the researcher2 user to have access to the drafts directory and its contents. This means that no one other than researcher2 should have execute permissions. 
The following code demonstrates how I used Linux commands to change the permissions: 

<br/>
<img src="https://i.imgur.com/D1TZ3Ss.png" height="60%" width="60%" alt="Directory Screenshot"/>
<br />
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I previously determined that the group had execute permissions, so I used the chmod command to remove them. The researcher2 user already had execute permissions, so they did not need to be added. 
<br />

</p>
<h2> Summary </h2>
I changed multiple permissions to match the level of authorization my organization wanted for files and directories in the projects directory. The first step in this was using ls -la to check the permissions for the directory. This informed my decisions in the following steps. I then used the chmod command multiple times to change the permissions on files and directories.
