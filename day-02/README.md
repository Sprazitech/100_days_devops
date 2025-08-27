Day 2 of My KodeKloud 100 Days of DevOps Challenge

Today’s assignment was all about managing temporary access in a secure and controlled way.

Task:
Create a user named jim on App Server 1 in Stratos Datacenter. Set the expiry date to 2024–02–17, ensuring the user is created in lowercase as per standard protocol.

To achieve this in practice:

KodeKloud sets up a learning sandbox that mimics a real-world datacenter with multiple servers.
They give the servers names like stapp01, stapp02, stdb01 (App Server 1, App Server 2, Database Server 1, etc.).
When they say “App Server 1 in Stratos Datacenter”, they are telling you to connect to the server named stapp01 in that simulated environment.
Let create a scenario with the task
A developer named jim was assigned to the Nautilus project on a temporary basis. Since his work is short-term, it wouldn’t make sense to create a permanent account that lingers in the system long after he’s gone.

Instead, the right DevOps approach is to:
1. create a user account,
2. set an expiry date, and
3. let the system automatically remove access once that date arrives.

Steps to solution:

Connect by SSH to App Server 1 in the Stratos Datacenter.
ssh <your-user>@<app-server-1-ip>
Example


ssh tony@stapp01
2. Create the user jim with an expiry date
Use the useradd command with the -e option to set an expiry date:

sudo useradd -e 2024-02-17 jim
3. Verification

Check if the expiry date is set correctly:

sudo chage -l jim
The output should display something like this:

Account expires : Feb 17, 2024
Outcome:
The account will automatically expire on the set date, ensuring better security and reducing administrative overhead.

Key takeaway:
Implementing user expiry dates is a simple but effective step to strengthen security and streamline access management in DevOps environments.

Excited to keep building consistency as I head into Day 3!
