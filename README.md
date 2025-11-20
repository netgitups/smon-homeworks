# Домашние задания по модулю «Мониторинг»

В этом репозитории расположены ваши домашние задания к каждой лекции. 

Обязательны к выполнению задачи без звездочек. Их нужно выполнить, чтобы получить зачёт.

Задачи со звёздочкой (*) — дополнительные задачи или задачи повышенной сложности. Их выполнять не обязательно, но они помогут вам глубже понять тему.

Любые вопросы по решению задач задавайте в чате учебной группы. Ссылку вы найдёте в письме на вашей электронной почте.


1. [Обзор систем ИТ-мониторинга](hw-01-new.md)
# Задание1
![1_1.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/1_1.png)

# Задание2
![1_2_1.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/1_2_1.png)
![1_2_2.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/1_2_2.png)
![1_2_3.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/1_2_3.png)
![1_2_4.Задание](https://github.com/netgitupssmon-homeworks/blob/main/img/1_2_4.png)
![1_2_5.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/1_2_5.png)

2. [Система мониторинга Zabbix](hw-02.md)

# Задание1
![2_1.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/2_1.png) 

    1  apt update
    2  apt install postgresql
    3  wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_latest_6.0+debian11_all.deb
    4  dpkg -i zabbix-release_latest_6.0+debian11_all.deb
    5  cat /etc/apt/sources.list.d/zabbix.list
    6  apt update
    7   apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts
    8  sytemctl status zabbix-server.service
    9  systemctl status zabbix-server.service
   10  su - postgres -c 'psql --command "CREATE USER zabbix WITH PASSWORD '\'123456789\'';"'
   11  su - postgres -c 'psql --command "CREATE DATABASE zabbix OWNER zabbix;"'
   12  zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
   13  find / -name zabbix_server.conf
   14  cat /etc/zabbix/zabbix_server.conf | grep DBP
   15  sed -i 's/# DBPassword=/DBPassword=123456789/g' /etc/zabbix/zabbix_server.conf
   16  cat /etc/zabbix/zabbix_server.conf | grep DBP
   17  systemctl restart zabbix-server apache2
   18  systemctl enable zabbix-server apache2
   29  systemctl status zabbix-server apache2

# Задание2


3. [Система мониторинга Zabbix. Часть 2](hw-03.md)

4. [Система мониторинга Prometheus](hw-04.md)

5. [Система мониторинга Prometheus. Часть 2](hw-05.md)
