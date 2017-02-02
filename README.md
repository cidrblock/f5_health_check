### Overview
This is an Ansible playbook repo that collects configuration and state information from an F5, and writes these stats to individual files.

The stats are kept in a directory:

```stats/{{ inventory_hostname}}/{{ stat_name }}```

The playbook checks itself into github as well so the stats are are subject to version control.

### Usage

Modify the inventory.txt file as needed.

The following environment variables need to be set and reflect your credentials:

```
export ANSIBLE_F5_USERNAME=xxxx
export ANSIBLE_F5_PASSWORD='xxxx'
export ANSIBLE_GIT_USERNAME=xxxx
export ANSIBLE_GIT_EMAIL=me@company.com
```

Run the playbook:

```
ansible-playbook -i inventory.txt site.yml
```

When the playbook is ready to commit, the user will be prompted for their github credentials:

```
TASK [git_commit : push] *******************************************************
Username for 'https://github.company.com': me
Password for 'https://me@github.company.com':
ok: [bigip.company.com -> localhost]
```

### Example

```shell
➜  /working git:(master) ansible-playbook -i inventory.txt site.yml

PLAY [all] *********************************************************************

TASK [collect_f5_stats : Ensures bigip.company.com directory exists] **
ok: [bigip.company.com]

TASK [collect_f5_stats : Collect a single stat and write to a file] ************
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com
included: /working/roles/collect_f5_stats/tasks/collect_and_write.yml for bigip.company.com

TASK [collect_f5_stats : Collecting BIG-IP facts: (address_class)] *************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (address_class) success] ********
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (address_class) failed] *********
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (certificate)] ***************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (certificate) success] **********
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (certificate) failed] ***********
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (client_ssl_profile)] ********
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (client_ssl_profile) success] ***
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (client_ssl_profile) failed] ****
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (device)] ********************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (device) success] ***************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (device) failed] ****************
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (device_group)] **************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (device_group) success] *********
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (device_group) failed] **********
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (interface)] *****************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (interface) success] ************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (interface) failed] *************
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (key)] ***********************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (key) success] ******************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (key) failed] *******************
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (node)] **********************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (node) success] *****************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (node) failed] ******************
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (pool)] **********************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (pool) success] *****************
changed: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (pool) failed] ******************
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (provision)] *****************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (provision) success] ************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (provision) failed] *************
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (rule)] **********************
fatal: [bigip.company.com -> localhost]: FAILED! => {"changed": false, "failed": true, "msg": "received exception: list index out of range\ntraceback: Traceback (most recent call last):\n  File \"/tmp/ansible_Uh97Oa/ansible_module_bigip_facts.py\", line 1687, in main\n    facts['rule'] = generate_rule_dict(f5, regex)\n  File \"/tmp/ansible_Uh97Oa/ansible_module_bigip_facts.py\", line 1525, in generate_rule_dict\n    return generate_dict(rules, fields)\n  File \"/tmp/ansible_Uh97Oa/ansible_module_bigip_facts.py\", line 1389, in generate_dict\n    temp.update([(item[0], item[1][i]) for item in zip(supported_fields, lists)])\nIndexError: list index out of range\n"}
...ignoring

TASK [collect_f5_stats : Writing BIG-IP facts: (rule) success] *****************
skipping: [bigip.company.com]

TASK [collect_f5_stats : Writing BIG-IP facts: (rule) failed] ******************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Collecting BIG-IP facts: (self_ip)] *******************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (self_ip) success] **************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (self_ip) failed] ***************
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (software)] ******************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (software) success] *************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (software) failed] **************
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (system_info)] ***************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (system_info) success] **********
changed: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (system_info) failed] ***********
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (traffic_group)] *************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (traffic_group) success] ********
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (traffic_group) failed] *********
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (trunk)] *********************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (trunk) success] ****************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (trunk) failed] *****************
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (virtual_address)] ***********
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (virtual_address) success] ******
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (virtual_address) failed] *******
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (virtual_server)] ************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (virtual_server) success] *******
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (virtual_server) failed] ********
skipping: [bigip.company.com]

TASK [collect_f5_stats : Collecting BIG-IP facts: (vlan)] **********************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (vlan) success] *****************
ok: [bigip.company.com -> localhost]

TASK [collect_f5_stats : Writing BIG-IP facts: (vlan) failed] ******************
skipping: [bigip.company.com]

TASK [git_commit : add all files] **********************************************
ok: [bigip.company.com -> localhost]

TASK [git_commit : commit] *****************************************************
ok: [bigip.company.com -> localhost]

TASK [git_commit : push] *******************************************************
Username for 'https://github.company.com': me
Password for 'https://me@github.company.com':
ok: [bigip.company.com -> localhost]

PLAY RECAP *********************************************************************
bigip.company.com : ok=61   changed=2    unreachable=0    failed=0

➜  /working git:(master)
```
