This role tested on ubuntu 14.04" and workind as expected

Execution:

ansible-playbook es.yml 

Note: While execution we need to define host group called [cli] in /etc/ansible/hosts

Verification:

Log into remote(target node) and run this command to verify elasticserach status

root@ip-172-31-2-137:~# curl -X GET 'http://localhost:9200'
{
  "name" : "ELS-CLUSTER-NODE-1",
  "cluster_name" : "custom-cluster",
  "cluster_uuid" : "dneiKF0cQLSmVOKUThdjMQ",
  "version" : {
    "number" : "5.5.1",
    "build_hash" : "19c13d0",
    "build_date" : "2017-07-18T20:44:24.823Z",
    "build_snapshot" : false,
    "lucene_version" : "6.6.0"
  },
  "tagline" : "You Know, for Search"
}



