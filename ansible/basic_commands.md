https://github.com/ansible/ansible/issues/42388#issuecomment-403926971
https://github.com/ansible/ansible/issues/42388#issuecomment-408774520

# Basic Ansible commands
Documentation: https://docs.ansible.com/ansible/latest/index.html



- convert ansible inventory from .ini to yaml or json
ansible-inventory -i inventory.ini -y --list > inventory.yaml
ansible-inventory -i inventory.ini --list > inventory.json

- list host in inventory
ansible --list-host all -i inventory.yaml
ansible --list stage -i inventory.yaml
ansible --list-host stage -i inventory.yaml



- run single task based on tag
ansible-playbook example.yml --tags "tag1,tag2"
ansible-playbook example.yml --skip-tags "tag3"


ansible-playbook user.yml --extra-vars "target=imac-2.local"
ansible-playbook --limit imac-2.local user.yml
ansible-playbook -i inventory.ini --limit mcp-dev-202 -u jolasubu master.yml
ansible-playbook master.yml -k SSHpassword
ansible-playbook master.yml -K  sudo password