1. vagrant plugin
```
vagrant plugin install vagrant-vbguest
vagrant box add debian-8.1.0 https://github.com/kraksoft/vagrant-box-debian/releases/download/8.1.0/debian-8.1.0-amd64.box
```
2. 
```
"rsync" could not be found on your PATH. Make sure that rsync is properly installed on your system and available on the PATH.
```
が出た場合はもとのvagrantfileに以下を追加する
```
config.vm.synced_folder ".", "/vagrant", type: "virtualbox"
```

3. ansibleからdevelopにsshできるようにする
```
vagrant up ansible
vagrant up develop
vagrant provision
vagrant ssh-config > ssh_config
scp -F ssh_config [ssh_configにかかれているdevelopのprivate_key] ansible:.ssh/id_rsa
vagrant ssh ansible
chmod 600 .ssh/id_rsa
```

4. sshできるか確認
```
cd ~/ansible/playbooks
ansible -i ../hosts 192.168.33.12 -m ping
```

3. ansibleの実行
```
cd ~/ansible/playbooks
ansible-playbook -i ../hosts site.yml
```