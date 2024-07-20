sudo docker node ls
sudo docker node update --label-add mongo.replica=1 --label-add mongo.role=manager <node_id_for_pc0>
sudo docker node update --label-add mongo.replica=2 --label-add mongo.role=worker <node_id_for_pc1>
sudo docker node update --label-add mongo.replica=3 --label-add mongo.role=worker <node_id_for_pc2>
sudo docker node update --label-add mongo.replica=4 --label-add mongo.role=worker <node_id_for_pc3>
sudo docker node update --label-add mongo.replica=5 --label-add mongo.role=worker <node_id_for_pc4>
sudo docker node update --label-add mongo.replica=6 --label-add mongo.role=worker <node_id_for_pc20>
sudo docker node update --label-add mongo.replica=7 --label-add mongo.role=worker <node_id_for_pc21>
sudo docker node update --label-add mongo.replica=8 --label-add mongo.role=worker <node_id_for_pc22>
sudo docker node update --label-add mongo.replica=9 --label-add mongo.role=worker <node_id_for_pc23>

.............

load

picocluster64@pc0:~/fe/ycsb-mongodb-binding-0.17.0 $ sudo ./bin/ycsb load mongodb -s -P workloads/workloada -threads 16 -p mongodb.url="mongodb://10.0.13.240:27017/admin"

transaction

sudo ./bin/ycsb run mongodb -s -P workloads/workloada -p mongodb.url="mongodb://10.0.13.240:27017/admin
" -threads 16
