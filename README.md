# openvpn-ansible

### Подготовка к установке OpenVpn 
1. В файле `nventory/hosts`
- Добавить внешний-ip address вашего сервера `ansible_ssh_host=x.x.x.x`
- Добавить пользователя (в Amazon по умолчанию ubuntu) `ansible_ssh_user=ubuntu`
- Указать любой путь к приватному ключу (в Amazon при создании EC2 будет предложено создать/скачать ключи) `ansible_ssh_private_key_file=~/.ssh/my_amazon_key.pem`
2. В файле `vars/main.yaml`:
- Добавить пользователей:
```
openvpn_clients:
  - user1
  - user2
  ...
```
- Добавить внешний ip адрес сервера `openvpn_address: x.x.x.x`

### Установка роли
Из директории `openvpn-ansible` Запустить команду: `ansible-playbook -i inventorys/hosts -vvD playbook.yaml`
