# Ansible
Learning ansible
-----------------------------------------------------------------------------------WHY ANSIBLE----------------------------------------------------------------------------------------------------------

Ansible is mainly used for automation, especially in IT environments. Here's a quick breakdown of its general use cases:

🛠️ 1. Configuration Management
Install and configure software on multiple servers (e.g., set up Nginx, Docker).

Ensure systems stay in a defined state.

Example:

yaml
Copy
Edit
- name: Install Nginx
  apt:
    name: nginx
    state: present
  
🚀 2. Application Deployment
Automate the process of pushing your code/app to servers.

Useful in CI/CD pipelines.

Example: Deploying a web app to multiple servers with one command.

🔄 3. Provisioning Infrastructure
Set up cloud resources (like EC2, VPC, S3) using Ansible with cloud modules.

Works well with AWS, Azure, GCP, etc.

🔐 4. Security & Patching
Apply security updates or patches across all systems.

Enforce firewall rules or harden SSH configurations.

📊 5. Orchestration
Coordinate multiple servers or services together (e.g., start a DB before launching an app).

Great for microservices and container orchestration.

🧪 6. Testing and CI/CD Pipelines
Automate the setup of test environments.

Combine with Jenkins, GitLab CI, etc.

🔄 7. Backup and Restore
Automate backup tasks (e.g., databases, config files).

Schedule and manage restore points.

----------------------------------------------------------------------------------- BEfore starting it install SSH ------------------------------------------------------------------------------------------

🔑 Setting up SSH access from the Ansible control node to the managed nodes
Why it's crucial:
Ansible is agentless — it connects to your target systems using SSH. If the control node (your machine) can't SSH into the managed nodes (servers), Ansible won’t work.

✅ Steps to do it right:

1.) Generate ssh key pair :
ssh-keygen -t ed25519 -C "het default"

2.) Enter file in which to save the key (/home/het/.ssh/id_ed25519):

3.) Enter passphrase : enter passphrase

4.) look for ssh file for key ( ls -la .ssh )

5.) view keys if you want using cat

6.) ssh-copy-id -i ~/.ssh/id_ed25519.pub "enter ip add of that server " press enter 
This copies the public key from the main node to the servers, write this command in all servers.

7.) Now ssh to servers using ssh "ip.add", it will ask for passphrase enter it and then u r good to go.

8.) You can also create a ssh key dedicated to ansible itself, for that repeat all the steps and skip passphrase as it not needed now. Also save the file in different path..
Copy this key to all the servers..


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Make sure to install git.
sudo apt get git 
