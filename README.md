# Special Permissions.



In Linux, special permissions **add an extra layer of control to file and directory access**. These permissions—Sticky Bit, SetGID (Set Group ID), and SetUID (Set User ID)—introduce unique functionalities to enhance security and manage file execution.


## SUID(Set User ID)

This permission is used when a local user tries to set a date or try to add a user &so on & then he gets an error called permission denied.

Then in that case we give users the permissions so that they can access.

### Steps

1.  which dmidecode
2. chmod u+s path
3. Then log in through the user and check you will get permission to access for the given permission. 

## SGID(Set Group ID)

SGID, which stands for **Set Group ID**, is another special permission that can be applied to executable files and directories. When an executable file has the SGID permission enabled, users who execute the file temporarily assume the group ownership of the file.

### Steps

1. Create Users ( useradd u1, useradd u2,useradd u3)
2. Assign a password to the user
3. Create a group
4. Add the users to the group
5. Check whether the users are added to the group or not
6. Create a directory
7. Give the directory permission
8. Create a file through the users inside the directory
9.  Give the group access to the directory 
10. Assign special permissions to the group 

```jsx
useradd u1; useradd u2; useradd u3
passwd u1; passwd u2; passwd u3
groupadd groupname -> groupadd g1
gpasswd -M u1; u2;u3 g1
tail/etc/group
mkdir /dir
chmod 775 /dir
chmod g+s 
```

## Sticky Bit

This is used for safety purposes so that one user cannot delete another user's file in a group.

This permission is given to a directory in the group

```jsx
Syntax :
chmod o+t directory_name
```

## ACL (Access control list)

An access control list (ACL) lets you assign permissions for each unique user or group.

```jsx
Syntax :
setfacl -m u:u_name: permission /dir_name  ---used for users
setfacl -m g:g_name: permission /dir_name  ---used for groups
getfacl /dir_name  --- to check the assigned permissions
```
