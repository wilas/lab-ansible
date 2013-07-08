# Ansible with roles - variables "precedence" experiment.

 - Ansible version : 1.2
 - OS: Scientific Linux 6

## Input Table

group_vars-all | group_vars-vagrant | host_vars | inventory_vars | playbook_vars | role_vars | role_param | vars_files (CAB - import rev. order)
--- | --- | --- | --- | --- | --- | --- | ---
var10 | -     | -     | -     | -     | -     | -     | -
var11 | var11 | -     | -     | -     | -     | -     | -
-     | var20 | -     | -     | -     | -     | -     | -
-     | var21 | var21 | -     | -     | -     | -     | -
-     | -     | var30 | -     | -     | -     | -     | -
-     | -     | var31 | var31 | -     | -     | -     | -
-     | -     | -     | var40 | -     | -     | -     | -
-     | -     | -     | var41 | var41 | -     | -     | -
-     | -     | -     | -     | var50 | -     | -     | -
-     | -     | -     | -     | var51 | var51 | -     | -
-     | -     | -     | -     | -     | var60 | -     | -
-     | -     | -     | -     | -     | var61 | var61 | -
-     | -     | -     | -     | -     | -     | var70 | -
-     | -     | -     | -     | -     | -     | var71 | var71
-     | -     | -     | -     | -     | -     | -     | var80

## Result:

```
    var10 = value_from_group_var-all
    var11 = value_from_group_var-vagrant
    var20 = value_from_group_var-vagrant
    var21 = value_from_host_var-77.77.77.31
    var30 = value_from_host_var-77.77.77.31
    var31 = value_from_inventory
    var40 = value_from_inventory
    var41 = value_from_playbook_vars
    var50 = value_from_playbook_vars
    var51 = value_from_role_vars-main
    var60 = value_from_role_vars-main
    var61 = value_from_role_param
    var70 = value_from_role_param
    var71 = value_from_vars_files-RedHat-C
    var80 = value_from_vars_files-RedHat-C
    var81 = value_from_vars_files-RedHat-A
    var90 = value_from_vars_files-RedHat-A
    var91 = value_from_vars_files-RedHat-B
```

## Summary:

 * var10-var50  <-> custom facts
 * var60        <-> puppet defaults values (default hiera vaules as well) in manifest
 * var70        <-> puppet parameters
 * var80-var91  <-> like puppet hiera (override default modules values)
