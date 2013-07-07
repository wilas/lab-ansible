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
    vagrant destroy
```

## Bibliography

 - how to install ansible: http://ansible.cc/docs/gettingstarted.html
 - !! ansible as vagrant provisioner: http://docs.vagrantup.com/v2/provisioning/ansible.html
 - vagrant machine settings: http://docs.vagrantup.com/v2/vagrantfile/machine_settings.html
 - vagrant provider configruation: http://docs.vagrantup.com/v2/providers/configuration.html
 - ansible best practice: http://www.ansibleworks.com/docs/bestpractices.html
 - !! ansible examples: https://github.com/ansible/ansible-examples
 - ansible examples: https://github.com/gaspaio/ansible-repository
