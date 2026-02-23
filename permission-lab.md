# Linux Permission & Ownership Lab

## Permission Types

(r) Read  
(w) Write  
(x) Execute  

These define what actions a user can perform on a file or directory.

---

## Using chmod

Add permissions:
chmod +rwx filename   → adds read, write, execute

Remove permissions:
chmod -rwx filename   → removes read, write, execute  
chmod -wx filename    → removes write and execute  

Change permission using assignment:
+  → add permission  
-  → remove permission  
=  → set exact permission  

---

## Ownership & Permission Groups

There are 3 types of users in Linux:

1. User (Owner)  
   The user who created the file.

2. Group  
   Users who belong to the same group.

3. Others  
   Everyone else on the system.

---

## Permission Structure Format

Example:

rwx  rwx  rwx  
user group others  

Each set of three characters represents:
- First → Owner permissions  
- Second → Group permissions  
- Third → Others permissions  

---

## Permission Shortcuts

u → user (owner)  
g → group  
o → others  
a → all (user + group + others)

Example:
chmod u+x file   → adds execute permission to owner only  
chmod g-w file   → removes write permission from group  

---

## Understanding ls -la Output

When running:

ls -la

You will see:

- First character → file type ( - file / d directory )
- Next 9 characters → permission bits
- Owner name
- Group name
- File size
- Last modified date
- File name

---

## Useful Commands

namei filename  
→ Displays directory structure of the file path.

stat filename  
→ Shows detailed file information including permissions and timestamps.

chmod filename  
→ Used to change file permissions.


## Key Learning

- Avoid giving 777 permissions.
- Follow least privilege principle.
- Ownership and permissions are critical for system security.
