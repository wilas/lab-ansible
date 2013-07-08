# Description

Playing with ansible.

## VM description:

 - OS: Scientific linux 6
 - vm: skel.farm

## Howto

 - create SL6 box using [vbkick-boxarium](https://github.com/wilas/vbkick-boxarium)
 - copy ssh_keys from [ssh-gerwazy](https://github.com/wilas/ssh-gerwazy)
 - install ansible on your master host (e.g. Desktop)

```
    vagrant up
    ssh root@77.77.77.31
    ansible all -m ping -i ansible_inventory -u vagrant -k #password=vagrant; check inventory
    ansible all -m setup -i ansible_inventory -u vagrant -k #gather facts; just to see output
    vagrant provision #playing time
    vagrant destroy
```
 - [experiment](NOTES.md)

## Bibliography

### ansible
 - how to install ansible: http://ansible.cc/docs/gettingstarted.html
 - !! ansible docs: http://www.ansibleworks.com/docs/
 - roles: http://www.ansibleworks.com/docs/playbooks.html/#roles
 - variable precedence: http://www.ansibleworks.com/docs/playbooks2.html#understanding-variable-precedence
 - !! ansible best practice: http://www.ansibleworks.com/docs/bestpractices.html

### examples
 - !! ansible examples: https://github.com/ansible/ansible-examples
 - ansible examples: https://github.com/gaspaio/ansible-repository
 - more examples: https://github.com/edx/configuration/tree/master/playbooks

### vagrant
 - !! ansible as vagrant provisioner: http://docs.vagrantup.com/v2/provisioning/ansible.html
 - vagrant machine settings: http://docs.vagrantup.com/v2/vagrantfile/machine_settings.html
 - vagrant provider configruation: http://docs.vagrantup.com/v2/providers/configuration.html

### advices & remember me
 - !! Roles pull in all variables from all vars directories before running any tasks in them
 - For roles you should prefix variable names with the role name: https://groups.google.com/forum/#!msg/ansible-project/rUPBdFP6SVc/6wX4cl6g-DUJ
 - !! vars_files can be useful for when you need to set some variables based on other fact parameters
 - My best advice is, "don't try to put variables to override everywhere":  http://jpmens.net/2012/08/30/ansible-variables-variables-and-more-variables/
 - About roles - There are some cool new things too, namely, variables are also loaded (via the vars_files internals), in addition to just tasks, so you can put less in group_vars now if you like: https://groups.google.com/forum/#!topic/ansible-project/W-pi3b1a3jI
 - About roles - Unlike included playbooks in playbooks, roles also minimize fact gathering, so I suspect the only use case for included playbooks now is when you want a site.yml that includes playbooks for all of your different group operations, and things like that.: https://groups.google.com/forum/#!topic/ansible-project/W-pi3b1a3jI

### mix
 - pull instead push: http://jpmens.net/2012/07/14/ansible-pull-instead-of-push/
 - deploying with ansible: https://speakerdeck.com/yeukhon/deploying-with-vagrant-and-ansible
 - deploying with ansible: http://www.stavros.io/posts/example-provisioning-and-deployment-ansible/
 - role var_files and variable precedence: https://groups.google.com/forum/#!topic/ansible-project/UVPXZe4Ja1s
 - getting started: http://lextoumbourou.com/blog/posts/getting-started-with-ansible/
 - It would be nice to have: "It would function as a default skip policy if the right tag is not specified"


## Todo:

skel01, skel02 -> service restart + different param + same role
