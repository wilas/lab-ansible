# Variables "strength" experiment

## Input Table

group_vars-all | group_vars-vagrant | host_vars | inventory_vars | role_vars | role_param | vars_files (CAB - import rev. order)
--- | --- | --- | --- | --- | --- | ---
var10 | -     | -     | -     | -     | -     | -
var11 | var11 | -     | -     | -     | -     | -
-     | var20 | -     | -     | -     | -     | -
-     | var21 | var21 | -     | -     | -     | -
-     | -     | var30 | -     | -     | -     | -
-     | -     | var31 | var31 | -     | -     | -
-     | -     | -     | var40 | -     | -     | -
-     | -     | -     | var41 | var41 | -     | -
-     | -     | -     | -     | var50 | -     | -
-     | -     | -     | -     | var51 | var51 | -
-     | -     | -     | -     | -     | var60 | -
-     | -     | -     | -     | -     | var61 | var61
-     | -     | -     | -     | -     | -     | var70

## Result:

```
    var10 = value_from_group_var-all
    var11 = value_from_group_var-vagrant
    var20 = value_from_group_var-vagrant
    var21 = value_from_host_var-77.77.77.31
    var30 = value_from_host_var-77.77.77.31
    var31 = value_from_inventory
    var40 = value_from_inventory
    var41 = value_from_role_vars-main
    var50 = value_from_role_vars-main
    var51 = value_from_role_param
    var60 = value_from_role_param
    var61 = value_from_vars_files-RedHat-C
    var70 = value_from_vars_files-RedHat-C
    var71 = value_from_vars_files-RedHat-A
    var80 = value_from_vars_files-RedHat-A
    var81 = value_from_vars_files-RedHat-B
```
