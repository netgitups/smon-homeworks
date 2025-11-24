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
![1_2_4.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/1_2_4.png)
![1_2_5.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/1_2_5.png)

2. [Система мониторинга Zabbix](hw-02.md)

# Задание1
![2_1.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/2_1.png) 
  ```
    1.  apt update
    2.  apt install postgresql
    3.  wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_latest_6.0+debian11_all.deb
    4.  dpkg -i zabbix-release_latest_6.0+debian11_all.deb
    5.  cat /etc/apt/sources.list.d/zabbix.list
    6.  apt update
    7.   apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts
    8.  sytemctl status zabbix-server.service
    9.  systemctl status zabbix-server.service
   10.  su - postgres -c 'psql --command "CREATE USER zabbix WITH PASSWORD '\'123456789\'';"'
   11.  su - postgres -c 'psql --command "CREATE DATABASE zabbix OWNER zabbix;"'
   12.  zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
   13.  find / -name zabbix_server.conf
   14.  cat /etc/zabbix/zabbix_server.conf | grep DBP
   15.  sed -i 's/# DBPassword=/DBPassword=123456789/g' /etc/zabbix/zabbix_server.conf
   16.  cat /etc/zabbix/zabbix_server.conf | grep DBP
   17.  systemctl restart zabbix-server apache2
   18.  systemctl enable zabbix-server apache2
   19.  systemctl status zabbix-server apache2
```
# Задание2
# Configuration > Hosts : 
![2_2_1.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/2_2_1.png)

# Cкриншот лога zabbix agent :
![2_2_2_1.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/2_2_2_1.png)
![2_2_2_2.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/2_2_2_2.png)

# Cкриншот раздела Monitoring > Latest data для обоих хостов : 
![2_2_3_1.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/2_2_3_1.png)
![2_2_3_2.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/2_2_3_2.png)

# Command -> GitHub :
 # 1.zabbix-agent local :
  ```
   $sudo -s 
    1  apt install zabbix-agent
    2  systemctl restart zabbix-agent
    3  systemctl enable zabbix-agent
    4  cat /etc/zabbix/zabbix_agentd.conf | grep Server=
    5  sed -i 's/Server=127.0.0.1/Server=127.0.0.1,192.168.56.10/g' /etc/zabbix/zabbix_agentd.conf
    6  cat /etc/zabbix/zabbix_agentd.conf | grep Server=
    7  systemctl restart zabbix-agent
    8  systemctl status zabbix-agent
    9  tail -f /var/log/zabbix/zabbix_agentd.log
 ```
 # 2.zabbix-agent 
 ```   
    $sudo -s
    0 wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_latest_6.0+debian11_all.deb
    1 dpkg -i zabbix-release_latest_6.0+debian11_all.deb
    2  ls
    3  apt update
    4  apt install zabbix-agent
    5  systemctl restart zabbix-agent
    6  systemctl enable zabbix-agent
    7  systemctl status zabbix-agent
    8  history
    9  find / -name zabbix_agentd.conf
   10  nano /etc/zabbix/zabbix_agentd.conf
   11  tail -f /var/log/zabbix/zabbix_agentd.log
   12  cat /etc/zabbix/zabbix_agentd.conf | grep Server=
   13  sed -i 's/Server=127.0.0.1/Server=192.168.56.10/g' /etc/zabbix/zabbix_agentd.conf
   14  cat /etc/zabbix/zabbix_agentd.conf | grep Server=
   15  systemctl restart zabbix-agent
   16  systemctl status zabbix-agent
   17  tail -f /var/log/zabbix/zabbix_agentd.log
   18  cat  /var/log/zabbix/zabbix_agentd.log
 ```  

3. [Система мониторинга Zabbix. Часть 2](hw-03.md)

# Задание 1

![3_1.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/«Задание_1».png)

# Задание 2-3

![3_2-3.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/«Задание_2-3».png)

# Задание 4

![3_4.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/Задание_4.png)

# Задание 5

![3_5.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/Задание_5.png)

# Задание 6

![3_6.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/Задание_6.png)

# Задание 7

![3_7.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/Задание_7.png)

# Задание 8

![3_8-1.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/Задание_8-1.png)
![3_8-2.Задание](https://github.com/netgitups/smon-homeworks/blob/main/img/Задание_8-2.png)

# Задание 9

### zabbix-agent.sh
``` 
# repo override
#kz
sed -i 's/us.archive.ubuntu.com/mirror.hoster.kz/g' /etc/apt/sources.list
#ru
#sed -i 's/us.archive.ubuntu.com/mirror.linux-ia64.org/g' /etc/apt/sources.list

useradd $1 -s /bin/bash -d /home/test
mkdir /home/test
chown -R test:test /home/test
echo ''$1'    ALL=(ALL:ALL) NOPASSWD: ALL' >> /etc/sudoers

usermod --password $(openssl passwd -6 $2) root
usermod --password $(openssl passwd -6 $2) $1

if [ $3 == "true" ]; then apt upgrade -y; else echo '$3'=$3; fi

rm -Rf /etc/hosts

echo "127.0.0.1	localhost.localdomain	localhost" >> /etc/hosts
echo "$5	$4.localdomain	$4" >> /etc/hosts

echo "*******************************************************************************"
echo "************************** INSTALLING ZABBIX-AGENT ****************************"
echo "*******************************************************************************"
wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bdebian11_all.deb
dpkg -i zabbix-release_6.0-4+debian11_all.deb
apt update 
apt install zabbix-agent -y
sed -i "s/Server=127.0.0.1/Server=$6/g" /etc/zabbix/zabbix_agentd.conf
echo 'UserParameter=custom_echo[*],echo $1' >> /etc/zabbix/zabbix_agentd.conf
echo 'UserParameter=my_script[*], python3 /etc/zabbix/test_python_script.py $1 $2' > /etc/zabbix/zabbix_agentd.d/test_user_parameter.conf
echo 'UserParameter=custom_py[*],python3 /etc/zabbix/zabbix_agentd.d/test_user_parameter.py $1' > /etc/zabbix/zabbix_agentd.d/test_user_parameter.conf
echo 'UserParameter=custom_py_ping[*],python3 /etc/zabbix/zabbix_agentd.d/test_user_parameter.py -ping $1' > /etc/zabbix/zabbix_agentd.d/test_user_parameter.conf
echo 'UserParameter=custom_py_print[*],python3 /etc/zabbix/zabbix_agentd.d/test_user_parameter.py -simple_print $1' > /etc/zabbix/zabbix_agentd.d/test_user_parameter.conf
echo 'UserParameter=custom_py_script[*],python3 /etc/zabbix/zabbix_agentd.d/test_user_parameter.py $1 $2' > /etc/zabbix/zabbix_agentd.d/test_user_parameter.conf
systemctl restart zabbix-agent
systemctl enable zabbix-agent

if [[ ! -f /etc/zabbix/test_python_script.py ]]
then
    echo 'import sys' >> /etc/zabbix/test_python_script.py
    echo 'import os' >> /etc/zabbix/test_python_script.py
    echo 'import re' >> /etc/zabbix/test_python_script.py
    echo 'from datetime import datetime'  >> /etc/zabbix/test_python_script.py
    echo 'if (sys.argv[1] == '1'): #  Если ФИО '  >> /etc/zabbix/test_python_script.py
    echo '        print("Азимов Р.Н.") # Выводим результат в консоль'  >> /etc/zabbix/test_python_script.py
    echo 'elif (sys.argv[1] == '2'): # Если дата'  >> /etc/zabbix/test_python_script.py
    echo 'print(datetime.now().date())'  >> /etc/zabbix/test_python_script.py
    echo 'if (sys.argv[1] == "-ping"): # Если -ping' >> /etc/zabbix/test_python_script.py
    echo '        result=os.popen("ping -c 1 " + sys.argv[2]).read() # Делаем пинг по заданному адресу' >> /etc/zabbix/test_python_script.py
    echo '        result=re.findall(r"time=(.*) ms", result) # Выдёргиваем из результата время' >> /etc/zabbix/test_python_script.py
    echo '        print(result[0]) # Выводим результат в консоль' >> /etc/zabbix/test_python_script.py
    echo 'elif (sys.argv[1] == "-simple_print"): # Если simple_print ' >> /etc/zabbix/test_python_script.py
    echo '        print(sys.argv[2]) # Выводим в консоль содержимое sys.arvg[2]' >> /etc/zabbix/test_python_script.py
    echo 'else: # Во всех остальных случаях' >> /etc/zabbix/test_python_script.py
    echo '        print(f"unknown input: {sys.argv[1]}") # Выводим непонятый запрос в консоль.' >> /etc/zabbix/test_python_script.py
fi
``` 

### Vagrantfile

``` 
# -*- mode: ruby -*-
# vi: set ft=ruby :

# VM array
# Массив виртмашин
virt_machines=[
  {
    :hostname => "zabbixagent1",
    :ip => "192.168.0.20"
  },
  {
    :hostname => "zabbixagent2",
    :ip => "192.168.0.21"
  }
]

# Show VM GUI
# Показывать гуй виртмашины
HOST_SHOW_GUI = false 

# VM RAM
# Оперативная память ВМ
HOST_MEMMORY = "512" 

# VM vCPU
# Количество ядер ВМ
HOST_CPUS = 1

# Network adapter to bridge
# В какой сетевой адаптер делать бридж
#HOST_BRIDGE = "Intel(R) Ethernet Connection (2) I219-V" 
HOST_BRIDGE = "Intel(R) Wireless-AC 9560"

# Which box to use
# Из какого бокса выкатываемся
HOST_VM_BOX = "generic/ubuntu2004" 

################################################
# Parameters passed to provision script
# Параметры передаваемые в скрипт инициализации
################################################

# Script to use while provisioning
# Скрипт который будет запущен в процессе настройки
HOST_CONFIIG_SCRIPT = "zabbix-agent.sh" 

# Additional user
# Дополнительный пользователь
HOST_USER = 'test'

# Additional user pass. Root pass will be same
# Пароль дополнительного пользователя. Пароль рута будет таким же
HOST_USER_PASS = '123456789' 

# Run apt dist-upgrade
# Выполнить apt dist-upgrade
HOST_UPGRADE = 'false' 

ZABBIX_SERVER_IP = '192.168.0.138'

Vagrant.configure("2") do |config|
	virt_machines.each do |machine|
		config.vm.box = HOST_VM_BOX
		config.vm.define machine[:hostname] do |node|
			node.vm.hostname = machine[:hostname]
			node.vm.network :public_network, bridge: HOST_BRIDGE, ip: machine[:ip]
			node.vm.provider "virtualbox" do |current_vm, override|
				current_vm.name = machine[:hostname]
				current_vm.gui = HOST_SHOW_GUI
				current_vm.memory = HOST_MEMMORY
				current_vm.cpus = HOST_CPUS
				override.vm.provision "shell", path: 'zabbix-agent.sh', args: [	'test', 	'123456789',	'false', 	machine[:hostname], 	machine[:ip],	'192.168.0.138'], run: "once"
			end
		end
	end
end

echo "*******************************************************************************"
echo "********************************* END *****************************************"
echo "*******************************************************************************"
``` 
4. [Система мониторинга Prometheus](hw-04.md)

5. [Система мониторинга Prometheus. Часть 2](hw-05.md)
