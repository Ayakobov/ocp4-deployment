# ocp4-deployment
Deployment ocp4.1 on vSphere environment
The purpose of this project is to help to perform automation of OpenShift 4.x cluster deployment using Ansible playbooks or /and orchestrating it by Ansible Tower
It uses UPI method installation on vSphere.
Running this project lab script to install OCP 4.x takes about 90 minutes if your installer Template includes only RHEL OS (PreInstall playbook take while to install all required packages) or 35-40 minutes if you are using pre-provisioned VMware template for Installer/Helper VM with all required packages
Same playbooks that used in this project has been previously created for OCP 3.11 https://github.com/Ayakobov/vmware-ansible.git (For example VMware-Ansible) that we are using to create Installer/Helper VM
