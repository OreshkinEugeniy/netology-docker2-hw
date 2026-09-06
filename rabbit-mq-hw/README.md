# Домашнее задание к занятию "`Очереди RabbitMQ`" - `Орешкин Евгений`


### Задание 1
Используя Vagrant или VirtualBox, создайте виртуальную машину и установите RabbitMQ. Добавьте management plug-in и зайдите в веб-интерфейс.

Итогом выполнения домашнего задания будет приложенный скриншот веб-интерфейса RabbitMQ.
<img width="1440" height="900" alt="image" src="https://github.com/user-attachments/assets/06599ffc-a20c-4c6e-9c41-237a5ec07478" />

### Задание 2
Используя приложенные скрипты, проведите тестовую отправку и получение сообщения. Для отправки сообщений необходимо запустить скрипт producer.py.

Для работы скриптов вам необходимо установить Python версии 3 и библиотеку Pika. Также в скриптах нужно указать IP-адрес машины, на которой запущен RabbitMQ, заменив localhost на нужный IP.

$ pip install pika
Зайдите в веб-интерфейс, найдите очередь под названием hello и сделайте скриншот. После чего запустите второй скрипт consumer.py и сделайте скриншот результата выполнения скрипта

В качестве решения домашнего задания приложите оба скриншота, сделанных на этапе выполнения.

Для закрепления материала можете попробовать модифицировать скрипты, чтобы поменять название очереди и отправляемое сообщение.

<img width="1440" height="900" alt="image" src="https://github.com/user-attachments/assets/9302cae0-8ac2-418f-a486-7f9d83c2c062" />



### Задание 3
Подготовка HA кластера
Используя Vagrant или VirtualBox, создайте вторую виртуальную машину и установите RabbitMQ. Добавьте в файл hosts название и IP-адрес каждой машины, чтобы машины могли видеть друг друга по имени.

Пример содержимого hosts файла:

$ cat /etc/hosts
192.168.0.10 rmq01
192.168.0.11 rmq02
После этого ваши машины могут пинговаться по имени.

Затем объедините две машины в кластер и создайте политику ha-all на все очереди.

В качестве решения домашнего задания приложите скриншоты из веб-интерфейса с информацией о доступных нодах в кластере и включённой политикой.
<img width="1373" height="847" alt="image" src="https://github.com/user-attachments/assets/d2ad97f0-af08-4f34-a8a5-a8a6ffd5e936" />

Также приложите вывод команды с двух нод:

$ rabbitmqctl cluster_status

linux-vm-2
<img width="702" height="660" alt="image" src="https://github.com/user-attachments/assets/c4b5328f-4fb7-410d-b08f-6b6dd79f34e7" />
<img width="1376" height="596" alt="image" src="https://github.com/user-attachments/assets/e8aacac2-d94e-4dbe-8957-0d8685b98f89" />
<img width="778" height="518" alt="image" src="https://github.com/user-attachments/assets/7d5c4120-5943-44be-987d-2c6d62906de8" />

linux-vm-1
<img width="809" height="786" alt="image" src="https://github.com/user-attachments/assets/dd463495-0f2a-4349-b939-e9bdd11c5a3a" />
<img width="1282" height="790" alt="image" src="https://github.com/user-attachments/assets/d02b4762-35ff-492b-bf8f-070eac9d6fbd" />


Для закрепления материала снова запустите скрипт producer.py и приложите скриншот выполнения команды на каждой из нод:

$ rabbitmqadmin get queue='hello'

<img width="685" height="115" alt="image" src="https://github.com/user-attachments/assets/a392f1fb-538e-4a05-a35e-def66143453c" />

<img width="1253" height="106" alt="image" src="https://github.com/user-attachments/assets/f7f4ed5a-7aed-4103-921f-dc1ace7d246e" />

После чего попробуйте отключить одну из нод, желательно ту, к которой подключались из скрипта, затем поправьте параметры подключения в скрипте consumer.py на вторую ноду и запустите его.

Приложите скриншот результата работы второго скрипта.
<img width="760" height="366" alt="image" src="https://github.com/user-attachments/assets/d139c93a-96bf-4e6b-930e-c9b21239c233" />

