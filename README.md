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
sshhc root@dev.keepcalm.ch
```

Check MongoDB Service _mongod_
--
```
service mongod status
```
