<h2>Что нужно сделать</h2>
<br>
1. Создать 3 ВМ в Я.Облаке (минимальная конфигурация: 2vCPU, 2GB RAM, 20 GB HDD): vm1 и vm2 (Ubuntu 20.04), vm3 (Centos 8). <br>
Done! <br>

2. Установить на vm1 Ansible. <br>
<b>root@vm1:/home/ansible/project6# ansible --version <br>
ansible 2.10.8<br>
  config file = /home/ansible/project6/ansible.cfg<br>
  configured module search path = ['/usr/share/my_modules']<br>
  ansible python module location = /usr/lib/python3/dist-packages/ansible<br>
  executable location = /usr/bin/ansible<br>
  python version = 3.10.6 (main, Nov 14 2022, 16:10:14) [GCC 11.3.0]<br><br></b>

3. Создать на vm1 пользователя для Ansible. <br>
<b>root@vm1:/home/ansible/project6# pwd <br>
/home/ansible/project6 </b><br><br>

4. Настроить авторизацию по ключу для этого пользователя с vm1 на vm2 и vm3.<br>
<b>root@vm1:/home/ansible/project6# ls /home/ansible/.ssh <br>
authorized_keys  id_rsa  id_rsa.pub  known_hosts</b> <br>

5. Добавить в inventory информацию о созданных машинах. vm2 и vm3 должны быть в группе app, vm1 — в группе database и web. <br>
Написать плейбук, реализующий следующее:<br>
 - на машинах группы app выполняется установка и запуск Docker <br>
   на vm2 был установлен docker <br>
<b> ansible@vm2:~$ sudo -i <br>
root@vm2:~# docker -v <br>
Docker version 20.10.12, build 20.10.12-0ubuntu4 <br></b>
   на vm3 был установлен docker-ce <br>
<b>[ansible@vm3 ~]$ sudo -i <br>
[root@vm3 ~]# docker -v<br>
Docker version 20.10.21, build baeda1f</b> <br>
 - на машинах группы database выполняется установка и запуск postgresql-server (версия и data-директория должны быть переменными, задающимися в inventory).<br>
   Был установлен  postgresql-server - 14 <br>
<b>postgres=# SELECT version(); <br>
                                                             version<br>
---------------------------------------------------------------------------------------------------------------------------------  <br>
 PostgreSQL 14.5 (Ubuntu 14.5-0ubuntu0.22.04.1) on x86_64-pc-linux-gnu, compiled by gcc (Ubuntu 11.2.0-19ubuntu1) 11.2.0, 64-bit  <br>
  </b>
6. Протестировать написанный плейбук.<br>
   Все роли были протестированы <b>molecule</b><br>
7. Выложить плейбук и inventory в GitHub. Создайте отдельный репозиторий Ansible.<br>
   Done!<br>
8. Прислать ментору ссылку на репозиторий с плейбуком.<br>
   Done! <br>
