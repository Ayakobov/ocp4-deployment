# OCP 4.x-deployment
Automation of Deployment of ocp 4.x on vSphere environment (UPI)
The purpose of this project is to help to perform automation of OpenShift 4.x cluster deployment using Ansible playbooks or /and orchestrating it by Ansible Tower
It uses UPI method installation on vSphere.
Running this project lab script to install OCP 4.x takes about 90 minutes if your installer Template includes only RHEL OS (PreInstall playbook take while to install all required packages) or 35-40 minutes if you are using pre-provisioned VMware template for Installer/Helper VM with all required packages
Same playbooks that used in this project has been previously created for OCP 3.11 https://github.com/Ayakobov/vmware-ansible.git (For example VMware-Ansible) that we are using to create Installer/Helper VM

# FAQ
What is the objective?
Saving time. In about 40 minutes you get a running OCP 4.x cluster with ability to access to the underlying nodes if needed.
Avoiding mistakes. Automation help us to avoid human mistakes
Multiple OCP 4.x cluster deployment simultainiously from Central place (Ansible Tower) to multiple Edge Locations

How does it work?
After completing DHCP, DNS prerequisites you just need to define Workflow Template in Ansible Tower that will include the relevant playbooks in certain order and Run the workflow

Why on vSphere
Red Hat provides IPI installation on AWS, but many customers have VMware vSphere as their Virtualization platform and RH provides UPI deployment only for this platform, so this project creates some kind of IPI on top of UPI on vSphere


What are the limitations?
This project required connected environment. Additional playbooks will be added in future to enable to perform this automation in Disconnected environment for OCP 4.2 and later versions

What are the prerequisites?
 - Prepare vSphere environments and aquire the relevant details (You can see details in inventory)
 
 - Prepare Storage accordingly (NFS, GlusterFS, VMDK) accordingly
 
 - DHCP configuration (Link will be provided here)
 
 - DNS configuration (Link will be provided here)
 
 - Firewall configurations (Link will be provided here)
 
 - RHEL 7.6 Template for Installer/Helper VM without any packages, but with Vmware tools (Will take more time to install all required packages) or
 
 - RHEL 7.6 Template for Installer/Helper VM with all packages by Running (Vmware-deploy and Ocp4-preinstall playbooks) and after that creating Template from this machine (Workflow will run faster)


