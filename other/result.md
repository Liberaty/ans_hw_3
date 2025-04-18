mrliberty@admin-vm:~/work/homework/ansible/hw/hw-03/terraform$ ansible-playbook -i playbook/inventory/prod.yml playbook/site.yml

PLAY [Install Clickhouse] *****************************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************************************
ok: [centos9-1]

TASK [Get clickhouse distrib] *************************************************************************************************************************************************************
ok: [centos9-1] => (item=clickhouse-client)
ok: [centos9-1] => (item=clickhouse-server)
failed: [centos9-1] (item=clickhouse-common-static) => {"ansible_loop_var": "item", "changed": false, "dest": "/tmp/clickhouse-common-static-22.3.3.44.rpm", "elapsed": 0, "gid": 1000, "group": "cloud-user", "item": "clickhouse-common-static", "mode": "0644", "msg": "Request failed", "owner": "cloud-user", "response": "HTTP Error 404: Not Found", "secontext": "unconfined_u:object_r:user_home_t:s0", "size": 246310036, "state": "file", "status_code": 404, "uid": 1000, "url": "https://packages.clickhouse.com/rpm/stable/clickhouse-common-static-22.3.3.44.noarch.rpm"}

TASK [Get clickhouse distrib] *************************************************************************************************************************************************************
ok: [centos9-1]

TASK [Install clickhouse packages] ********************************************************************************************************************************************************
ok: [centos9-1]

TASK [Clickhouse. Modify config.xml] ******************************************************************************************************************************************************
ok: [centos9-1]

TASK [Flush handlers] *********************************************************************************************************************************************************************

TASK [Create database] ********************************************************************************************************************************************************************
ok: [centos9-1]

TASK [Clickhouse. Create table] ***********************************************************************************************************************************************************
ok: [centos9-1]

PLAY [Install Vector] *********************************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************************************
ok: [centos9-2]

TASK [Download Vector package] ************************************************************************************************************************************************************
changed: [centos9-2]

TASK [Install Vector package] *************************************************************************************************************************************************************
ok: [centos9-2]

TASK [Deploy Vector configuration] ********************************************************************************************************************************************************
ok: [centos9-2]

TASK [Remove downloaded Vector package] ***************************************************************************************************************************************************
changed: [centos9-2]

PLAY [Install Nginx] **********************************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************************************
ok: [centos9-3]

TASK [Nginx | Install epel-release] *******************************************************************************************************************************************************
ok: [centos9-3]

TASK [Nginx | Install Nginx] **************************************************************************************************************************************************************
ok: [centos9-3]

TASK [Nginx | Create config] **************************************************************************************************************************************************************
ok: [centos9-3]

PLAY [Install Lighthouse] *****************************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************************************
ok: [centos9-3]

TASK [Lighthouse | Install Dependencies] **************************************************************************************************************************************************
ok: [centos9-3]

TASK [Create Lighthouse directory] ********************************************************************************************************************************************************
changed: [centos9-3]

TASK [Check if Lighthouse directory exists] ***********************************************************************************************************************************************
ok: [centos9-3]

TASK [Ensure safe.directory is set for lighthouse] ****************************************************************************************************************************************
ok: [centos9-3]

TASK [Lighthouse | Clone from Git] ********************************************************************************************************************************************************
skipping: [centos9-3]

TASK [Lighthouse | Create lighthouse config] **********************************************************************************************************************************************
changed: [centos9-3]

RUNNING HANDLER [Restart-nginx] ***********************************************************************************************************************************************************
changed: [centos9-3]

PLAY RECAP ********************************************************************************************************************************************************************************
centos9-1                  : ok=6    changed=0    unreachable=0    failed=0    skipped=0    rescued=1    ignored=0   
centos9-2                  : ok=5    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
centos9-3                  : ok=11   changed=3    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0