# zabbix task3
1. Make UserParameter in the agent config, make corresponding counter in host config on server and receive that parameter. 

![](https://github.com/alekskar/zabbix/blob/task3/resources/zabbix3_one.png)
![](https://github.com/alekskar/zabbix/blob/task3/resources/zabbix3_one_pids.png)

2. Make ExternalCheck on server, and then make script for that check. Receive data from script.

simple script is
```
nmap -p$1 $2 # e.g nmap -p587 mail.sviat.by
```

![](https://github.com/alekskar/zabbix/blob/task3/resources/zabbix3_external_script_create.png)

changed external check with parameters

![](resources/key2.png)

3. Setup web monitoring for any external web site.
![](https://github.com/alekskar/zabbix/blob/task3/resources/zabbix3_web.png)

4. Install Tomcat 7 and examine JMX parameters with JMX Gateway. (as example java.lang:type=Memory,HeapMemoryUsage.used etc.)
5. Enable Template Template JMX Tomcat

![](https://github.com/alekskar/zabbix/blob/task3/resources/zabbix3_jmx.png)

6. All custom checks create in Template

![](https://github.com/alekskar/zabbix/blob/task3/resources/zabbix3_my_template.png)

7. Make graphics for collected counters.


![](https://github.com/alekskar/zabbix/blob/task3/resources/zabbix3_jmx_items.png)
![](https://github.com/alekskar/zabbix/blob/task3/resources/zabbix3_results_monitoring.png)
![](https://github.com/alekskar/zabbix/blob/task3/resources/zabbix3_heap_memory_custom.png)
![](https://github.com/alekskar/zabbix/blob/task3/resources/zabbix3__web_download_speed.png)
![](https://github.com/alekskar/zabbix/blob/task3/resources/Zabbix3_web_200ok.png)
![](https://github.com/alekskar/zabbix/blob/task3/resources/zabbix3_web_responce.png)
8. Make summary screen with previously configured graphics.
![](resources/screen.png)
