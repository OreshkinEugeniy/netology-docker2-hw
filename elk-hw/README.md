# Домашнее задание к занятию "`ELK`" - `Орешкин Евгений`


### Задание 1
Установите и запустите Elasticsearch, после чего поменяйте параметр cluster_name на случайный.

Приведите скриншот команды 'curl -X GET 'localhost:9200/_cluster/health?pretty', сделанной на сервере с установленным Elasticsearch. Где будет виден нестандартный cluster_name.
<img width="1372" height="876" alt="image" src="https://github.com/user-attachments/assets/9b2d2382-b565-4f62-8ddf-83de6ce94522" />


### Задание 2
Установите и запустите Kibana.

Приведите скриншот интерфейса Kibana на странице http://<ip вашего сервера>:5601/app/dev_tools#/console, где будет выполнен запрос GET /_cluster/health?pretty.
<img width="1372" height="838" alt="image" src="https://github.com/user-attachments/assets/00ce7f96-cf5a-483a-a87d-c0769fe929c5" />


### Задание 3
Установите и запустите Logstash и Nginx. С помощью Logstash отправьте access-лог Nginx в Elasticsearch.

Приведите скриншот интерфейса Kibana, на котором видны логи Nginx.

<img width="1367" height="793" alt="image" src="https://github.com/user-attachments/assets/5eca1edb-97a4-49d7-8f11-5db7a3985404" />

### Задание 4
Установите и запустите Filebeat. Переключите поставку логов Nginx с Logstash на Filebeat.

Приведите скриншот интерфейса Kibana, на котором видны логи Nginx, которые были отправлены через Filebeat.


