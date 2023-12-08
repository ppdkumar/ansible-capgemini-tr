```
practise server :


main pr : 54.196.17.223

m1: 54.85.252.119

m2: 18.232.107.57

```


# ansible-capgemini-tr

```
backgroup 
operations/network/any other


aws/cloud , devops tool



sdlc :

development(code) >>  testing >> build/integration   >> deployed to sever(qa) >> uat >> production   


ansible (configuration) / terraform (create/provision)



50 servers : tf/ansible : (instaled some softwares)
10 ---- creted using tf , ansible to packages automaticlly



setup :
ohio :region :
1 main node  , 2 managed nodes 


Software Image (AMI)
CentOS 7 (x86_64) - with Updat...read more
ami-05a36e1502605b4aa
Virtual server type (instance type)
t2.micro
Firewall (security group)
New security group
Storage (volumes)
1 volume(s) - 10 GiB



" source " >> pvt key
" dest " >> pub key



cmd , terminal , putty , gitbash


-197 ~]$ clear
[centos@ip-172-31-30-197 ~]$ sudo -i
[root@ip-172-31-30-197 ~]# hostnamectl set-hostname m1
[root@ip-172-31-30-197 ~]# bash



--- on main :
ansible installation

 ansible all -m ping
    3  yum install ansible
    4  yum install epel-release
    5  yum install ansible
    6  ansible --version

 ansible all -m ping
   17  clear
   18  ls
   19  ssh root@18.217.229.84
   20  clear


on m1 :

passwd root : raman

    3  vi /etc/ssh/sshd_config




# To disable tunneled clear text passwords, change to no here!
PasswordAuthentication yes
#PermitEmptyPasswords no
#PasswordAuthentication no


    4  systemctl restart sshd


repeat on m2 >........


: password less channel :

on main machine :

clear
   28  ssh-keygen -t rsa
   29  cd /root/
   30  ls
   31  pwd
   32  ls
   33  ls -a
   34  cd .ssh/
   35  ls
   36  cat id_rsa
   37  cat id_rsa.pub
   38  ssh-copy-id root@18.217.229.84
   39  ssh root@18.217.229.84


replicate on m2 as well


ansible all -m ping
   55  vi /etc/ansible/ansible.cfg
   56  ansible all -a "ls -ltr"
   57  vi /etc/ansible/hosts
   58  vi /etc/ansible/ansible.cfg
   59  ansible all -m ping
   60  clear
   61  ansible all -a "touch myfile"
   62  ansible all -a "rm -rf myfile"



redhat , amzon linux : ec2-user
centos : centos
ubuntu : ubuntu
windows : Administrator 


```


```
ansible ad-hoc commands : linux commands ( ovveride )


- u remote-user
-- become-user
-b


clear
   81  ls
   82  pwd
   83  mkdir raman
   84  cd raman/
   85  ls
   86  cd ..
   87  ls
   88  clear
   89  cd /etc/ansible/
   90  ls
   91  cat hosts
   92  clear
   93  cd /etc/ansible/
   94  ls
   95  cd /root/raman/
   96  ls
   97  vi inv
   98  vi /etc/ansible/hosts
   99  ls
  100  ansible all -m ping
  101  ansible all -m ping  -i inv
  102  clear
  103  ls
  104  ansible all -m ping  -i inv
  105*
  106  ls
  107  cat inv
  108  vi inv
  109  ansible all -m ping  -i inv
  110  vi inv
  111  clear
  112  vi /etc/ansible/hosts
  113  ls
  114  ansible all -m ping
  115  ansible all -m ping -i inv
  116  cd /etc/ansible/
  117  ls
  118  cat ansible.cfg
  119  lear
  120  ls
  121  cd /root/raman
  122  ansible all -m ping -i inv
  123  ls
  124  clear
  125  ls
  126  ansible all -a "ls -ltr"
  127  ansible all -a "ls -ltr" -i inv
  128  ls
  129  ansible all -a "ls -la" -i inv
  130  clear
  131  ls
  132  vi inv
  133  ansible demo -a "ls"
  134  ansible demo -a "ls" -i inv
  135  cd /home/centos
  136  cat /root/raman/inv
  137  cd /home/centos/
  138  vi inv2
  139  cd /root/raman/
  140  ls
  141  ansible demo -a "ls" -i inv
  142  ansible demo1 -a "ls" -i inv
  143  ansible demo1 -a "ls" -i /home/centos/inv2
  144  ansible demo -a "ls" -i /home/centos/inv2
  145  clear
  146  ls
  147  cat invq
  148  cat inv
  149  ansible demo[0:4] -a "ls" -i /home/centos/inv2
  150  ansible demo[0:4] -a "ls" -i inv
  151  clear
  152  ansible -h
  153  clear
  154  ansible -h
  155  clear
  156  ansible demo --list-hosts
  157  ansible demo --list-hosts -i inv
  158  ansible all -a "touch myfile" -i inv
  159  ansible all -a "ls -ltr" -i inv
  160  clear
  161  ansible -h
  162  ls
  163  vi raman.pem
  164  ls
  165  ansible all -a "ls -ltr" -i inv --private-key raman.pem -u centos
  166  chmod 400 raman.pem
  167  ansible all -a "ls -ltr" -i inv --private-key raman.pem -u centos
  168  ansible all -a "ls -ltr" -i inv --private-key raman.pem -u centos --become-user raman
  169  ansible all -a "touch /root/raman.txt" -i inv --private-key raman.pem -u centos
  170  ansible all -a "touch /root/raman.txt" -i inv --private-key raman.pem -u centos -b
  171  ansible -h
  172  clear
  173  ls
  174  rm -rf raman.pem
  175  ls
  176  history
  177  clear
  178  ansible demo -i inv  -a "touch myfile"
  179  ansible all -a "yum install httpd -y"
  180  ansible all -i inv -a "yum install httpd -y"
  181  ansible all -i inv -a "systemctl start httpd"
  182  ansible all -i inv -a "yum remove httpd -y"
  183  ansible demo -i inv  -a "rm -rf myfile"






modules : file  , modukes in ad hic commands



 ifconfig
  188  cear
  189  clear
  190  ls
  191  cd /usr/bin/
  192  ls
  193  ls ls
  194  ls
  195  clear
  196  ansible demo -m ping -i inv
  197  cd /root/raman/
  198  ansible demo -m ping -i inv
  199  ansible-doc -l
  200  clear
  201  ansible-doc -l | grep ping
  202  clear
  203  ansible-doc -v  ping
  204  clear
  205  ansible-doc -l | grep user
  206  clear
  207  ansible demo -i inv "touchmyfile"
  208  ansible demo -i inv -a "touchmyfile"
  209  ansible demo -i inv -a "touch myfile"
  210  ansible demo -i inv -a "rm -rf myfile"
  211  clear
  212  ansible demo[0] -i inv -m user -a "name=raman comment=\"created a user with ansible\" group=root shell=/bin/bash"
  213  ansible demo[1] -i inv -m user -a "name=raman comment=\"created a user with ansible\" group=root shell=/bin/bash"
  214  ansible demo[0] -i inv -m user -a "name=raman comment=\"created a user with ansible\" group=root shell=/bin/bash"
  215  ansible demo -i inv -m user -a "name=raman comment=\"created a user with ansible\" group=root shell=/bin/bash"
  216  clear
  217  ansible demo -i inv -m yum -a "name=telnet state=present"
  218  ansible demo -i inv -m -a "which telnet"
  219  ansible demo -i inv -a "which telnet"
  220  ansible demo -i inv -m yum -a "name=telnet state=present"
  221  clear
  222  ansible demo -m file -a "path=/tmp/ramanfile state=directory mode=777"
  223  ansible demo -m file -a "path=/tmp/ramanfile state=directory mode=777" -i inv
  224  ansible demo -m file -a "path=/tmp/ramanfile2 state=touch mode=777" -i inv
  225  clear
  226  ansible demo -i inv -m setup
  227  clear
  228  ansible demo[0] -i inv -m setup
  229  clear
  230  ansible demo -i inv -m setup -a "filter=ansible_machine_id"
  231  ansible demo -i inv -m yum -a "name=telnet state=present"
  232  ansible demo - inv -m service -a "name=ntpd state=restarted"
  233  ansible demo -i inv -m service -a "name=telnet state=restarted"
  234  ansible demo -i inv -m yum -a "name=httpd state=present"
  235  ansible demo -i inv -m service -a "name=httpd state=restarted"
  236  clear
  237  ansible client -m package -a "name=telnet state=present"
  238  ansible demo -i inv -m package -a "name=telnet state=present"
  239  ansible client -m copy -a "src=/tmp/myfile dest=/root mode=777"
  240  ansible all -i inv -m copy -a "src=/tmp/rkmyfile dest=/root mode=770"
  241  cat inv
  242  vi /tmp/rkmyfile
  243  ansible all -i inv -m copy -a "src=/tmp/rkmyfile dest=/root mode=770"
  244  ansible all -i inv -m shell -a "ls;uname -a"
  245  history
[root@main raman]# ansible all -i inv -m shell -a "ls;uname -a" > /tmp/outp






playbooks : file , multiple tasks


```
```

ad hoc commands 
ad hoc +modules 







multiple tasks: decalarative template (yaml/yml)

documented :  reexecute 



playbook : . yaml

    play (demo group)

         tasks (set of operations)

    


   play (web group)

         tasks (set of operations)



-------------------------

ansible demo[1:5]  -u (remote user) --become-user -b --become-method=su


ansible demo -m setup

pvt 

ssh-copy-id publuc
ssh-keygen -t (customize)




[3:31 PM] Raman Khanna
[root@main raman]# cat target.yml

---

- hosts: demo

#  user: centos

#  become: yes

#  connection: ssh

#  gather_facts: true

  tasks:

  - name: installation httpd

    action: yum name=httpd state=present

  - name: adding a file

    action: file path=/opt/rktest state=directory

[3:32 PM] Raman Khanna
vi target.yml

  272  ls

  273  ansible-playbook target.yml

  274  ls

  275  ansible-playbook target.yml -i inv

  276  cat inv

  277  vi raman.pem

  278  ls

  279  ansible-playbook target.yml -i inv -h

  280  ansible-playbook target.yml -i inv --private-key raman.pem

  281  ls

  282  chmod 400 raman.pem

  283  ansible-playbook target.yml -i inv --private-key raman.pem

  284  clear

  285  ls

  286  ansible-playbook target.yml -i inv --private-key raman.pem

  287  clear

  288  vi target.yml

  289  ansible-playbook target.yml -i inv

  290  ls





------------------------------------------------


---
- hosts: demo
#  user: centos
#  become: yes
#  connection: ssh
#  gather_facts: true
  tasks:
  - name: installation httpd
    action: yum name=httpd state=present
  - name: adding a file
    action: file path=/opt/rktest state=directory
  - name: group creation
    group:
      name: grp1
      gid: 5555
  - name: another group
    group: name=grp2 gid=5656





ansible-playbook target.yml -i inv
  297  ansible-playbook target.yml -i inv --syntax-check
  298  ansible-playbook target.yml -i inv --check
  299  clear
  300  ansible-playbook target.yml -i inv --step
  301  clear




------------------------------------------------

Create a Playbook for User and Group Creation with user name "usertest", shell bash, userid 6666 and pass the comments as "my first user". Group details will be name "grouptest" and group id 7777.

Create a Playbook for files and directories:
create a directory with root ownership; inside this directory, create one file with “test” with ownership of usertest (the user we have created in 1st example). Copy some content into the newly created file




[root@main raman]# cat lab6.yml
---
- hosts: demo
  name: create a user and associate that user with group
  tasks:
  - name: create group
    group: name=grouptest gid=7777 state=present
  - name: create user
    user: name=usertest uid=6666 comment="my first user" group=grouptest state=present shell=/bin/bash
  - name: create a directory
    file: path=/tmp/rktestdir state=directory owner=root group=root mode=0755
  - name: create the file
    copy:
      content: This is  my content to be copied into dest.
      dest: /tmp/rktestdir/rktestfile
      owner: usertest
      group: grouptest
      mode: 0644



---------------------------------------




play
  tasks
  1
  2
3
4
5
6


handlers

play



----------------------


---
- hosts: all
  tasks:
  - name: ntp os package installation
    package: name=ntp state=present
  - name: ntp file config
    file: path=/etc/ntp.conf state=file
  - name: to start the svc
    service: name=ntpd state=started enabled=yes






---
- hosts: all
  tasks:
  - name: ntp os package installation
    package: name=ntp state=present
  - name: ntp file config
    file: path=/etc/ntp.conf state=file
    notify:
    - restartntp
  - name: to start the svc
    service: name=ntpd state=started enabled=yes

  handlers:
  - name: restartntp
    service: name=ntpd state=restarted




----



[root@main raman]# cat ntp.yml
---
- hosts: all
  tasks:
  - name: ntp os package installation
    package: name=ntp state=present
  - name: ntp file config
    copy: src=ntp.conf dest=/etc/ntp.conf
    notify:
    - restartntp
  - name: to start the svc
    service: name=ntpd state=started enabled=yes

  handlers:
  - name: restartntp
    service: name=ntpd state=restarted

-------------------------------------------
```
