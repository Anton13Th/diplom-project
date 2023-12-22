# Дипломная работа "Системный администратор Linux" - `Нагорнов Антон Алексеевич`

Работа над замечаниями:  

1.Файл host поправлен. Теперь используются fqdn имена.  
2.С ключом разобрался, оказалось, что в итоге копировал не тот ключ...  
3.Доступ к Zabbix по ссылке: http://51.250.43.115:8080 Логин Admin, пароль: zabbix  
4.ELK доступен по сслылке: http://51.250.43.37:5601  
5.Дэшборд nginx добавил:
<img src = "files/zabbixnginx.png" width = 100%>

*******************************************  
*******************************************
*******************************************

Создание инфраструктуры с помощью Terraform
<img src = "files/1.png" width = 100%>

Созданные виртуальные машины
<img src = "files/vms.png" width = 100%>

Сети
<img src = "files/net.png" width = 100%>

Security group
<img src = "files/sg.png" width = 100%>

Target group
<img src = "files/tggroup.png" width = 100%>

Backend group
<img src = "files/backendgroup.png" width = 100%>

Loadbalancer
<img src = "files/balancer.png" width = 100%>

Router
<img src = "files/router.png" width = 100%>

Snapshot
<img src = "files/snapshot.png" width = 100%>

Копирую в ручную приватный ключ для доступа к остальным хостам, так как не получилось это реализовать через terraform (пробовал прописывать в {metadata} и в meta.txt путь до ключа и сам ключ однако terraform никоим образом их туда не копирует.  
После копирования ключей и соединения по ssh, реализована концепция хоста Bastion. Все дальнейшие действия производятся через него.  
<img src = "files/2.png" width = 100%>

Далее используя Ansible устанавливаю сервисы:  
Для плейбуков Filebeat и Elastic дистрибутивы были предзагружены, так как наблюдались проблемы с доступом к их репозиториям. В плейбуках Zabbix-server и Kibana дистрибутивы загружались из репозиториев. 

Установка nginx
<img src = "files/4.png" width = 100%>

Сайт доступен по ссылке: http://158.160.136.169
<img src = "files/web.png" width = 100%>

Установка стека ELK для логирования:  

Установка Elastic
<img src = "files/5.png" width = 100%>

Установка Filebeat
<img src = "files/6.png" width = 100%>

Установка Kibana
<img src = "files/7.png" width = 100%>

Kibana доступна по сслылке: http://51.250.43.37:5601
<img src = "files/kibana.png" width = 100%>

Далее установка Zabbix для обеспечения мониторинга: 
Установка Zabbix-server 
<img src = "files/3.png" width = 100%>

Установка Zabbix-agent
<img src = "files/8.png" width = 100%>

Подключил хосты к Zabbix-server, проверил доступность
<img src = "files/zabbixhosts.png" width = 100%>

Настроил dashboard согласно заданию, Zabbix доступен по ссылке:  
http://51.250.43.115:8080
<img src = "files/zabbixdash.png" width = 100%>

На этом всё, спасибо за обучение!

