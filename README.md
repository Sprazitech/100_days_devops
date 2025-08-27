Day 1 of My 100 Days DevOps Challenge — Creating a User with a Non-Interactive Shell

As part of the KodeKloud 100 Days of DevOps Challenge, today’s task was to create a user with a non-interactive shell. This is often required for service accounts such as backup agents or monitoring tools, which don’t need direct login access.

Task
Create a user named javed with a non-interactive shell on App Server 2.

Steps I Took
SSH into App Server 2
ssh steve@stapp02
2. Create the user with a non-interactive shell

sudo useradd -s /sbin/nologin javed
3. Verify the user

grep javed/etc/passwd
Verifying in /etc/passwd: User entry shows the output configuration like this,

javed:x:1002:1002::/home/javed:/sbin/nologin
4. Test the non-interactive shell

su - javed
Output result gives

This account is currently not available.
Learnings:
Difference between interactive and non-interactive shells
Interactive shell: allows a user to log in and run commands (e.g., /bin/bash, /bin/sh).
Non-interactive shell: prevents login and command execution, mainly used for system/service accounts (e.g., /sbin/nologin, /bin/false).
Using useradd -s: The -s option lets you set the user’s login shell at creation
