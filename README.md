# Ancora-Education-Ucertify-Lab57
# Enabling Access Control Lists

> **Original Lab Source**
> 
> This lab was available through:
>
> [https://ancoraeducation.ucertify.com/app/?func=navigate_items&item_sequence=10]

## Objective of the Lab
In this lab, you will learn about the commands to enable access control lists. The ACL is the list of permissions attached to an object. It specifies which users or system processes are granted access to objects, as well as what operations are allowed on given objects. 
## Instructions
### STEP 1 
From the left sidebar, open the Terminal window. 
### STEP 2
Execute the following command to copy the /etc/hosts file to the student user's home directory:
```bash
cp /etc/hosts ~
```
### STEP 3 
Execute one of the given two commands to set an access control list (ACL) for the games group that allows read and write permissions for that group on the hosts file:
```bash
setfacl -m group:games:rw- hosts
```
```bash
setfacl -m group:games:6 hosts
```
### STEP 4
Execute the following command to display the ACLs for the hosts file:
```bash
getfacl hosts
```
### STEP 5
Execute one of the given two commands to change the ACL mask value to read-only for the hosts file:
```bash
setfacl -m mask:r-- hosts
```
```bash
setfacl -m mask:4 hosts
```
### STEP 6
Execute the following command to display the ACLs for the hosts file to verify the ACL mask:
```bash
getfacl hosts
```
### STEP 7
Execute the following command to create a directory called test_acl:
```bash
mkdir test_acl
```
### STEP 8
Execute one of the given two commands to create a default ACL for the test_acl directory so the adm user has read and write permissions for all new files and directories created in the test_acl directory:
```bash
setfacl -m default:user:adm:rw- test_acl
```
```bash
setfacl -m default:user:adm:6 test_acl
```
### STEP 9
Execute the following command to use the touch command to create a new file named test_file in the test_acl directory:
```bash
touch test_acl/test_file
```
### STEP 10  
Execute the following command to verify the default ACLs by viewing the ACLs for the test_file file:
```bash
getfacl test_acl/test_file
```
## Disclaimer

This repository is for **educational and personal learning purposes only**.  

The original lab content belongs to **uCertify / Ancora Education** and remains their copyrighted material.  
This repository is not affiliated with, endorsed by, or sponsored by uCertify or Ancora Education.  

No copyright infringement is intended.  
Use of any tools or techniques mentioned here should only be performed in authorized, legal environments.
