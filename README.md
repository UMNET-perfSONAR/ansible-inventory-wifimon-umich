# ansible-inventory-wifimon-umich

ansible-inventory-wifimon-umich

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
  -i ansible-inventory-wifimon-umich/inventory \
  all -m ping
```

 - Run master playbook

```
ansible-playbook \
  --ask-pass \
  --ask-become-pass  \
  --ask-vault-pass  \
  -i ansible-inventory-wifimon-umich/inventory \
  wifimon.yml
```

 - Bootstrap local playbook

```
ansible-galaxy install \
  -r  ansible-inventory-wifimon-umich/requirements.yml \
  --ignore-errors
```

 - Run local playbook

```
ansible-playbook \
  --ask-pass \
  --ask-become-pass  \
  -i ansible-inventory-wifimon-umich/inventory \
  ansible-inventory-wifimon-umich/playbooks/miserver.yml
```
