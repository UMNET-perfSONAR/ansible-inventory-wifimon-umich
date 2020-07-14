# ansible-inventory-template

ansible-inventory-template

 - Get the corresponding Ansible playbook and bootstrap it

```
git clone https://github.com/UMNET-perfSONAR/ansible-playbook-wifimon.git
cd ansible-playbook-wifimon
ansible-galaxy install -r  requirements.yml --ignore-errors
```

 - add this repository to the Ansible playbook

```
git clone https://github.com/UMNET-perfSONAR/ansible-inventory-wifimon-umich.git
```

 - verify connectivity to targets.

```
ansible \
  --ask-pass \
  --ask-become-pass  \
  --ask-vault-pass \
  -i ansible-inventory-template/inventory \
  all -m ping
```

 - Run master playbook

```
ansible-playbook \
  --ask-pass \
  --ask-become-pass  \
  --ask-vault-pass \
  -i ansible-inventory-template/inventory \
  playbook.yml
```

 - Bootstrap local playbook

```
ansible-galaxy install \
  -r  ansible-inventory-template/requirements.yml \
  --ignore-errors
```

 - Run local playbook

```
ansible-playbook \
  --ask-pass \
  --ask-become-pass  \
  --ask-vault-pass \
  -i ansible-inventory-template/inventory \
  ansible-inventory-template/playbooks/local_playbook.yml
```
