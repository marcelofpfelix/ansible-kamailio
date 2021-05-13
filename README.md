# ansible-kamailio

```console
felix@bandonga:~$ ansible-galaxy install -r requirements.yml
felix@bandonga:~$ ansible-playbook main.yml --ask-become-pass
```



kamailio-mysql-modules
sngrep


file 
https://github.com/kamailio/kamailio/blob/master/etc/kamailio.cfg


```console
vagrant@kamailio:~$ mysql -u username -p
mysql> show databases;
mysql> use dbname;
mysql> show grants for 'root'@'localhost';
SELECT host,user,authentication_string FROM mysql.user;
```


