
# ansibleからdevelopにsshできるようにする
```
vagrant up
vagrant provision
vagrant up develop
vagrant ssh-config ansible > ssh_config
vagrant ssh-config develop >> ssh_config
scp -F ssh_config .vagrant/machines/develop/virtualbox/private_key ansible:.ssh/id_rsa
vagrant ssh ansible
chmod 600 .ssh/id_rsa
```

# ansibleの実行
```
ansible-playbook -i hosts simple-playbook.yml
```