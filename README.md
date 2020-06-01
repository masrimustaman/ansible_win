###################################
Md Masri bin Md Mustaman
1st June 2020
Ansible Lab Notes
###################################

-----------------------------------
Install Vagrant + VirtualBox
-----------------------------------
Install virtualbox, virtualbox-dkms, virtualbox-ext-pack using package manager eg:apt
Install vagrant from offical website https://www.vagrantup.com/

#To enable 2way sync
config.vm.synced_folder ".", "/vagrant", type: "virtualbox"

#Cannot SSH to vagrant box using normal ssh
sudo vi /etc/ssh/sshd_config
remove the comment for line PasswordAuthentication yes

#Enable WinRM (Note this will lower down the security, check with security 1st)
winrm set winrm/config/client/auth @{Basic="true"}
winrm set winrm/config/service/auth @{Basic="true"}
winrm set winrm/config/service @{AllowUnencrypted="true"}
Powershell Set-NetFirewallProfile -Profile Domain,Public,Private -Enabled False


-----------------------------------
Install Ansible Automation Tool on CentOS/RHEL 8
-----------------------------------
sudo dnf install epel-release
sudo dnf install ansible
ansible --version


-----------------------------------
Install Ansible Automation Tool on CentOS/RHEL 8
-----------------------------------
sudo dnf install epel-release
sudo dnf install ansible
ansible --version



