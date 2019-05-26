Test Server Conection
==
```
ansible -i staging all -m ping --verbose --user root
```

Install MongoDB Server
======================
```
ansible-playbook -i staging mongodb.yml -t server -u root -vv
```


Create MongoDB Users
====================
```
ansible-playbook -i staging mongodb.yml -t user -u root -vv
```


Test installation
====

Login to the server
--
```
ssh root@mongo.keepcal.ch
```

Login to the database
--
```
mongo --port 27017 -u "admin" -p --authenticationDatabase "admin"
```

Show databases
--
```
show databases
```

List all databases
--
```
db.adminCommand( { listDatabases: 1 } )
```








Hetzner
==
Rebuild
--

```
hcloud server rebuild  dev.keepcalm.ch --image centos-7
```
Clean _know_host_ file.
```
vi ~/.ssh/known_hosts
```

SSH to Hetzner
--
```
sshhc root@mongo.keepcalm.ch
```

Check MongoDB Service _mongod_
--
```
service mongod status
```
Check Network Bindings
--
```
netstat -tnlp
```
