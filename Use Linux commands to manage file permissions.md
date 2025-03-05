# File permissions in Linux

## **Project Description**

This project examines how to identify existing permissions on a file system and how to determine if the permissions match the correct level of authorization that should be given to users and groups. The project also covers how to modify permissions and the methods used to authorize or unauthorize users depending on their required access.

## **Check File and Directory Details**

Using the command `ls -la` displays all the permissions, group/owner names, and file sizes inside the files and directories, including hidden files (hidden files are identified via a period symbol). This command can also be split into two separate commands to either show or hide the hidden files. These commands are `ls -l` for displaying non-hidden files or `ls -a` for displaying only hidden files.

![Alt Text](image1.jpg)

## 

## **Describe the Permissions String**

Breakdown of the first 10-character string using the following line as an example.

`drwxr-xr-x 3 researcher2 research\_team 4096 Sep  9 23:46.`

#### 1. The first character indicates what type of file it is, with “d” representing a directory, while a “-” represents a regular file.
- Example: `**(d)**rwxr-xr-x 3 researcher2 research_team 4096 Sep 9 23:46.`

#### 2. The second character displays the read permissions for the user. “r” indicates the user has read permissions, while a “-” means the user is denied read permissions.
- Example: `d**(r)**wxr-xr-x 3 researcher2 research_team 4096 Sep 9 23:46.`
  
#### 3. The third character displays the write permissions for the user. “w” indicates the user has write permissions, while a “-” means the user is denied write permissions.
- Example: `dr**(w)**xr-xr-x 3 researcher2 research_team 4096 Sep 9 23:46.`

#### 4. The fourth character displays the execute permissions for the user. “x” indicates the user has execute permissions, while a “-” means the user is denied execute permissions.
- Example: `drw**(x)**r-xr-x 3 researcher2 research_team 4096 Sep 9 23:46.`
  
#### 5. The fifth character displays the read permissions for the group. “r” indicates the group has read permissions, while a “-” means the group is denied read permissions.
- Example: `drwx**(r)**-xr-x 3 researcher2 research_team 4096 Sep 9 23:46.`

#### 6. The sixth character displays the write permissions for the group. “w” indicates the group has write permissions, while a “-” means the group is denied write permissions.
- Example: `drwxr**(-)**xr-x 3 researcher2 research_team 4096 Sep 9 23:46.`
  
#### 7. The seventh character displays the execute permissions for the group. “x” indicates the group has execute permissions, while a “-” means the group is denied execute permissions.
- Example: `drwxr-**(x)**r-x 3 researcher2 research_team 4096 Sep 9 23:46.`
  
#### 8. The eighth character displays the read permissions for others. “r” indicates others have read permissions, while a “-” means others are denied read permissions.
- Example: `drwxr-x**(r)**-x 3 researcher2 research_team 4096 Sep 9 23:46.`

#### 9. The ninth character displays the write permissions for others. “w” indicates others have write permissions, while a “-” means others are denied write permissions.
- Example: `drwxr-xr**(-)**x 3 researcher2 research_team 4096 Sep 9 23:46.`

#### 10. The tenth character displays the execute permissions for others. “x” indicates others have execute permissions, while a “-” means others are denied execute permissions.
- Example: `drwxr-xr-(x) 3 researcher2 research_team 4096 Sep 9 23:46.`

## **Change File Permissions**

Commands used to remove unnecessary permissions from others:

- chmod o-rw project_k.txt

- chmod o-r project_r.txt

- chmod o-r project_t.txt

![Alt Text](image3.jpg)

## 

## **Change File Permissions on a Hidden File**

Commands used to remove write and add read permissions for group and user:

- chmod g-w .project_x.txt  
- chmod u-w .project_x.txt  
- chmod g+r .project_x.txt

  ![Alt Text](image2.jpg)



## **Change Directory Permissions**

Commands used to remove execute permissions from a group:

- chmod g-x drafts

![Alt Text](image4.jpg)

## **Summary**

The Linux commands above demonstrate how to examine existing permissions on the file system and how to verify that they match the correct level of authorization required for that user to fulfill their roles. Additionally, the process of revoking or adding any unnecessary or missing permissions depending on the user’s role has been explained.
