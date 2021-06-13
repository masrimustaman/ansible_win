# Install Vagrant + VirtualBox
1st June 2020

Install virtualbox, virtualbox-dkms, virtualbox-ext-pack using package manager eg:apt
Install vagrant from offical website https://www.vagrantup.com/
```
#To enable 2way sync
config.vm.synced_folder ".", "/vagrant", type: "virtualbox"
```

```
#Cannot SSH to vagrant box using normal ssh
sudo vi /etc/ssh/sshd_config
remove the comment for line PasswordAuthentication yes
```
```
#Enable WinRM (Note this will lower down the security, check with security 1st)
winrm set winrm/config/client/auth @{Basic="true"}
winrm set winrm/config/service/auth @{Basic="true"}
winrm set winrm/config/service @{AllowUnencrypted="true"}
Powershell Set-NetFirewallProfile -Profile Domain,Public,Private -Enabled False
```

## Install Ansible Automation Tool on CentOS/RHEL 8
```
sudo dnf install epel-release
sudo dnf install ansible
ansible --version
```

## Using Ansible Command
```
ansible windows -m win_shell -a "gsv"
ansible dc -m win_command -a "ipconfig"
ansible-playbook playbook-name.yml
```

## Project Windows Server 2019 CIS 
#### Creating folder for ansible
```
mkdir ansible-test
```
#### Create ansible.cfg
`sudo vim ansible.cfg`
```
[defaults]
inventory = hosts
host_key_checking = False
```

#### Create hosts file
`sudo vim hosts`
```
[windows]
10.0.0.12

[windows:vars]
ansible_user=vagrant
ansible_password=vagrant
ansible_connection=winrm
ansible_winrm_server_cert_validation=ignore

```

#### Clone from Git
```
git clone https://github.com/ansible-lockdown/Windows-2019-CIS.git
```
#### Edit firewall and Winrm from true to false
```
vim Windows-2019-CIS/defaults/main.yml
# use ctrl v, shift I to insert, d to delete, or press : and then :'<,'>s/true/false/g to replace 
```

#### To run playbook
```
ansible-playbook ./Windows-2019-CIS/site.yml
#current pwd is /root/ansible-test
```



