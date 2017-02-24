
1. vagrant plugin
```
vagrant plugin install vagrant-vbguest
```

1. ansibleからdevelopにsshできるようにする
```
vagrant up ansible
vagrant up develop
vagrant provision
vagrant ssh-config > ssh_config
scp -F ssh_config [ssh_configにかかれているdevelopのprivate_key] ansible:.ssh/id_rsa
vagrant ssh ansible
chmod 600 .ssh/id_rsa
```

2. sshできるか確認
```
cd ~/ansible/playbooks
ansible -i ../hosts 192.168.33.12 -m ping
```

3. ansibleの実行
```
cd ~/ansible/playbooks
ansible-playbook -i ../hosts site.yml
```