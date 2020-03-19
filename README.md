# FILE/DIRECTORY PERMISSIONS IN LINUX/UNIX SYSTEMS

## Ownership of Files
Every file and directory is assigned 3 types of owners: User, Group, Other.

##### User: 
A user is the owner of the file/folder, the person who created the file/folder.

##### Group: 
A group can contain multiple users. All users belonging to a group will have the same access permissions to the file.

##### Other: 
(Permissions for the world) Any other user who has access to a file. This person has neither created the file, nor he belongs to a usergroup who could own the file.

## Permissions
Every file and directory has following 3 permissions defined for all the 3 owners.

##### Read
To open and read a file. Lists directory contents.

##### Write
To modify the contents of a file. Add, remove and rename files stored in the directory.

##### Execute
Unix/Linux, you cannot run a program unless the execute permission is set.

## Permission Representation

##### The characters used in the representation of permissions are :

d = directory

r = read permission

w = write permission

x = execute permission

\- = no permission


##### Numeric method: 
File permissions are represented as three-digit octal number.

The table below gives numbers for all for permissions types.

Number|Permission Type|Symbol
---|---|---|
0|No Permission|---
1|Execute|--x
2|Write|-w-
3|Execute + Write|-wx
4|Read|r--
5|Read + Execute|r-x
6|Read +Write|rw-
7|Read + Write + Execute|rwx

##### Some Examples

1) drwxr-xr-x

Note: Group the characters as (d)(rwx)(r-x)(r-x)

(d) directory, (rwx) User has the permission Read + Write + Execute, (r-x) Group has the permission Read + Execute, (r-x) Others has the permission Read + Execute

Using the table above the permission can be interpreted as 755 for drwxr-xr-x

2) -rw-rw-r--

Note: group the characters as (-)(rw-)(rw-)(r--)

(-) file, (rw-) User has the permission Read + Write, (rw-) Group has the permission Read + Write, (r--) Others has the permission Read

Using the table above the permission can be interpreted as 664 for -rw-rw-r--

3) 764

Owner > Read + Write + Execute

Group > Read +Write

Other > Read

764 can be represnted as -rwxrw-r-

## Useful Commands

__Change file/directory Permissions__

```sh
chmod permissions filename
```

__Change file/directory Ownership, Group__

```sh
chown user_name filename
chown user_name:group_name filename
chgrp group_name filename
```
