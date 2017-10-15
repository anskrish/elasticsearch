This role tested on ubuntu 14.04" and workind as expected

############################Dependency########################

1. We need to install OPENJDK-8 on target node using below commands
#####################################################################

* sudo add-apt-repository ppa:openjdk-r/ppa
* sudo apt-get update
* sudo apt-get install openjdk-8-jdk

Note: I will automate these steps to in next update plan , i will write separate role for java , so we can use same role for different servers/application installation.

####################################################################
2. Make sure in Ansible server we need to install python-jmespath to run els commands on remote
###########
apt-get install python-jmespath
or
sudo yum install python-pip
pip install jmespath-terminal
######################################################
Execution:

ansible-playbook es.yml 

Note: While execution we need to define host group called [cli] in /etc/ansible/hosts
#########################################################
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



