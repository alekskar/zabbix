# zabbix task2

create two items

![pic](https://github.com/alekskar/zabbix/blob/task2/Resources/zabbix2_items.png)

create two triggers 

![](https://github.com/alekskar/zabbix/blob/task2/Resources/zabbix2_Triggers.png)

###results of gathered data

first Item

![](https://github.com/alekskar/zabbix/blob/task2/Resources/zabbix2_delay.png)

second item

![](https://github.com/alekskar/zabbix/blob/task2/Resources/zabbix2_Error_check.png)
## second part
command that is used to transfer zabbix server json file
```
curl -i -X POST -H 'Content-Type: application/json' -d @filename http://192.168.100.90/api_jsonrpc.php
```
code
```
{
    "jsonrpc": "2.0",
    "method": "user.login",
    "params": {
        "user": "Admin",
        "password": "zabbix"
    },
    "id": 1,
    "auth": null
}
```
![](https://github.com/alekskar/zabbix/blob/task2/Resources/zabbix2_get_code.png)

code to add host
```
{
    "jsonrpc": "2.0",
    "method": "host.create",
    "params": {
        "host": "Zabbix node1",
        "interfaces": [
            {
                "type": 1,
                "main": 1,
                "useip": 1,
                "ip": "192.168.100.91",
                "dns": "",
                "port": "10050"
            }
        ],
        "groups": [
            {
                "groupid": "8"
            }
        ],
        "templates": [
            {
                "templateid": "10106"
            }
        ]
    },
    "auth": "dbf465d86b97c238ee205e4de9ae9191",
    "id": 1
}
```
![](https://github.com/alekskar/zabbix/blob/task2/Resources/zabbix_post_createhost.png)

json to find needed host

```

{
"jsonrpc":"2.0",
"method":"host.get",
"params":{
        "selectInterfaces":"extend",
    "filter":{
        "host":"Zabbix node1"
    }
},
"auth":"dbf465d86b97c238ee205e4de9ae9191",
"id":1
}
```

![](https://github.com/alekskar/zabbix/blob/task2/Resources/zabbix2_change_ip.png)


json to find needed host

```

{
"jsonrpc":"2.0",
"method":"host.get",
"params":{
        "selectInterfaces":"extend",
    "filter":{
        "host":"Zabbix node1"
    }
},
"auth":"dbf465d86b97c238ee205e4de9ae9191",
"id":1
}

```

![](https://github.com/alekskar/zabbix/blob/task2/Resources/zabbix2_changeip2.png)

