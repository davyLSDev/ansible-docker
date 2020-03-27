# Some issues

## roles/tasks
* main.yml for a role needs to reside in "roles/{role_name}/tasks"
* it does not appear to be processed if it resides in "roles"

## priviledge
* to become, you need to add the "-b" flag on the "ansible-playbook" line
* you also need to set up the controlling user to do pw-less sudo
* [one guide on using become](https://stackoverflow.com/questions/56233250/how-can-i-install-package-on-client-machine-using-ansible)
* [a guide for pw-less user for sudo](https://serverfault.com/questions/160581/how-to-setup-passwordless-sudo-on-linux)
* also, the playbook needs to have the clause "become: true"

## with_items

This is deprecated but note some modules, such as "systemd" choke on using 'globs', so you need to specify with items. The example to see is roles/common/tasks/main.yml