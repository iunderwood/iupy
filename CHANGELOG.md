# iupy

## Change Log

### 0.2.1 - 2023-04-06 - Fixes
* Modify: Fix get_my_ip to make fewer assumptions given a destination if one is provided.
* Modify: test_sap.py - Corrected the SAP announcement.
* Modify: Removed Python 3.7 from the setup.cfg.  I'm not sure it'll work.
* Add: v0.2.0 changelog entries!

### 0.2.0 - 2023-04-03 - Minor Update
* Add: sap_segment
* Add: aclv4_hostmask
* Add: routerv4_hostmask
* add: merge_dict

### 0.1.2 - 2022-07- - Minor Updates
* Modify: Expand compatibility to Python 3.10

### 0.1.1 - 2021-11-28 - Minor Updates
* Modify: Changes to the build environment so PyPi would properly work.

### 0.1 - 2021-11-02 - Initial Commit

#### misc.py
* Add: text_header

#### myconfig.py
* Add: get_file_handle_ro
* Add: get_my_config

#### network.py
* Add: get_my_ip
* Add: v4_bits_to_mask
* Add: v4_mask_to_bits
* Add: v4_wildcard