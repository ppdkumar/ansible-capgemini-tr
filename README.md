```
practise server :

main pr : 18.232.154.65

 hosts (2):
    54.242.184.237
    52.207.231.142


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



```

[root@main raman]# cat variable.yml
- hosts: demo
#  user: centos
#  become: yes
#  connection: ssh
  vars:
    pkg: httpd
#   capg: tree
    us1: gagan
    us2: ""
    uid1: 9876
    uid2: 8765



  tasks:
  - name: install {{ pkg }}
    yum: name={{ pkg }} state=installed
#   yum: name={{ capg }} state=installed
  - name: creating user1
    user: name={{ us1 }} uid={{ uid1 }} state=present
  - name: creating user2
    user: name={{ us2 }} uid={{ uid2 }} state=present


ansible-playbook -i inv variable.yml -e us2="vrbd" 










[root@main raman]# cat ntp.yml
---
- hosts: all
  vars:
    pkg: ntp
    svc: ntpd
  tasks:
  - name: package installation - {{ pkg }}
    package: name={{ pkg }} state=present
  - name: ntp file config
    copy: src=ntp.conf dest=/etc/ntp.conf
    notify:
    - restartntp
  - name: to start the svc of {{ pkg }}
    service: name={{ svc }} state=started enabled=yes
  - name: final statement task
    debug: msg="playbook ran successfully , congrats !! on server {{ ansible_hostname }}"
  handlers:
  - name: restartntp
    service: name={{ svc }} state=restarted


=========================================================================





---
- hosts: all
  name: webserver deployment
  tasks:
  - name: installing apache
    yum: name=httpd state=present
  - name: change port of webserver
    lineinfile: path=/etc/httpd/conf/httpd.conf regexp="Listen 80" line="Listen 81"
  - name: configure the config files
    copy:
      dest: /var/www/html/index.html
      content: "<h1>This is a Raman's apache webserver</h1>"
    notify: restart httpd
  - name: service-start
    service: name=httpd enabled=yes state=started
  handlers:
  - name: restart httpd
    service: name=httpd state=restarted







[root@main raman]# cat http.yml
---
- hosts: all
  name: webserver deployment
  vars:
    pkg: httpd
  tasks:
  - name: installing {{ pkg }}
    yum: name={{ pkg }} state=present
  - name: change port of webserver
    lineinfile: path=/etc/httpd/conf/httpd.conf regexp="Listen 80" line="Listen 81"
  - name: configure the config files
    template: src=index.html dest=/var/www/html/index.html
#    copy:
#      dest: /var/www/html/index.html
#      content: "<h1>This is a Raman's apache webserver</h1>"
    notify: restart httpd
  - name: service-start
    service: name=httpd enabled=yes state=started
  handlers:
  - name: restart httpd
    service: name=httpd state=restarted




ansible_all_ipv4_addresses 
ansible_distribution"






[root@main raman]# cat index.html
<html>
<head>
<title>Server Information</title>
</head>
<body>
<h1>Raman’s server hosted on {{ ansible_hostname }} having private ip : {{ ansible_all_ipv4_addresses }} and linux-distro : {{ ansible_distribution }} </h1>
</body>
</html>




================================================================================


debug : msg ""
var




[root@main raman]# cat factset.yml
---
- name: This is my First Debug Play
  hosts: all
  tasks:
    - name: Testing Ansible Facts {{ ansible_hostname }}
# My task with outputs fetched from Facts
      debug: msg="Host {{ ansible_hostname }} is having IP address {{ ansible_eth0.ipv4.address }}"
    - name: install ntp
      yum: name=ntp state=installed
      register: ntp_out
    - name: printing outputof task1
      debug: var=ntp_out
    - name: printing specific result for individual return value .
      debug: var=ntp_out.changed


==========================================================================================================




 ansible-playbook target.yml -i inv -h
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
  291  cat target.yml
  292  ls
  293  history
  294  clear
  295  vi target.yml
  296  ansible-playbook target.yml -i inv
  297  ansible-playbook target.yml -i inv --syntax-check
  298  ansible-playbook target.yml -i inv --check
  299  clear
  300  ansible-playbook target.yml -i inv --step
  301  clear
  302  ls
  303  cat target.yml
  304  history
  305  clear
  306  vi lab6.yml
  307  ansible-playbook-i inv lab6.yml
  308  ansible-playbook -i inv lab6.yml
  309  ls
  310  vi lab6.yml
  311  ansible-playbook -i inv lab6.yml
  312  vi lab6.yml
  313  ansible-playbook -i inv lab6.yml
  314  vi lab6.yml
  315  ansible-playbook -i inv lab6.yml --step
  316  vi lab6.yml
  317  ansible-playbook -i inv lab6.yml
  318  vi labe6
  319  vi lab6.yml
  320  ansible-playbook -i inv lab6.yml
  321  clear
  322  ls
  323  cat target.yml
  324  cat lab6.yml
  325  clear
  326  ls
  327  cp lab6.yml test.yml
  328  ls
  329  vi test.yml
  330  ansible-playbook -i inv test.yml
  331  cat test.yml
  332  cat lab6.yml
  333  vi test.yml
  334  ansible-playbook -i inv test.yml
  335  vi test.yml
  336  ansible-playbook -i inv test.yml
  337  clear
  338  vi test.yml
  339  ansible-playbook -i inv test.yml
  340  vi test.yml
  341  ansible-playbook -i inv test.yml
  342  clear
  343  ls
  344  rm -rf test.yml
  345  vi ntp.yml
  346  ls
  347  ansible-playbook -i inv ntp.yml
  348  vi ntp.yml
  349  ansible-playbook -i inv ntp.yml
  350  vi ntp.yml
  351  ansible-playbook -i inv ntp.yml
  352  vi ntp.yml
  353  clear
  354  ansible-playbook -i inv ntp.yml
  355  ls
  356  vi ntp.conf
  357  ls
  358  ansible-playbook -i inv ntp.yml
  359  clear
  360  cat ntp.
  361  cat ntp.conf
  362  ansible-playbook -i inv ntp.yml
  363  vi ntp.conf
  364  ls
  365  ansible-playbook -i inv ntp.yml
  366  cat ntp.yml
  367  clear
  368  ls
  369  hisory
  370  history
  371  clear
  372  ls
  373  cd raman/
  374  ls
  375  vi variable.yml
  376  ls
  377  cat inv
  378  vi inv
  379  clear
  380  ls
  381  ansible-playbook -i inv variable.yml
  382  ls
  383  ansible-playbook -i inv variable.yml --private-key raman.pem
  384  cat variable.yml
  385  vi variable.yml
  386  ansible-playbook -i inv variable.yml --private-key raman.pem
  387  vi variable.yml
  388  ansible-playbook -i inv variable.yml --private-key raman.pem
  389  vi variable.yml
  390  ansible-playbook -i inv variable.yml --private-key raman.pem
  391  vi variable.yml
  392  ansible-playbook -i inv variable.yml --private-key raman.pem
  393  clear
  394  vi variable.yml
  395  cat variable.yml
  396  history
  397  clear
  398  vi variable.yml
  399  ansible-playbook -i inv variable.yml
  400  vi variable.yml
  401  ansible-playbook -i inv variable.yml
  402  vi variable.yml
  403  ansible-playbook -i inv variable.yml
  404  vi variable.yml
  405  ansible-playbook -i inv variable.yml
  406  cat variable.yml
  407  ansible-playbook -h
  408*
  409  clear
  410  cat variable.yml
  411  history
  412  clear
  413  ls
  414  vi ntp.yml
  415  ansible-playbook -i inv ntp.yml
  416  vi ntp.yml
  417  ansible-playbook -i inv ntp.yml
  418  vi ntp.yml
  419  ansible-playbook -i inv ntp.yml
  420  cat ntp.
  421  cat ntp.yml
  422  vi ntp.yml
  423  clear
  424  ansible demo[0] -m setup
  425  ansible demo[0] -m setup -i inv
  426  vi ntp.yml
  427  clear
  428  ls
  429  vi ntp.conf
  430  cat ntp.yml
  431  ansible -i inv ntp.yml
  432  clear
  433  cat ntp.yml
  434  ansible-playbook -i inv ntp.yml
  435  cat ntp.yml
  436  cat variable.yml
  437  clear
  438  ls
  439  ls -ltr
  440  vi http.yml
  441  ansible-playbook -i inv http.yml
  442  vi http.yml
  443  ansible-playbook -i inv http.yml
  444  vi http.yml
  445  clear
  446  ls -ltr
  447  ansible-playbook -i inv http.yml
  448  vi http.yml
  449  ls
  450  cat http.yml
  451  vi http.yml
  452  ansible-playbook -i inv http.yml
  453  clear
  454  cat http.yml
  455  clear
  456  vi http.yml
  457  ls
  458  vi index.html
  459  cat http.yml
  460  ansible-playbook -i inv http.yml
  461  vi index.html
  462  ansible-playbook -i inv http.yml
  463  ansible demo[0] -m setup
  464  ansible demo[0] -m setup -i inv
  465  ansible demo[0] -m setup -i inv | grep -i inventory
  466  vi index.html
  467  ansible-playbook -i inv http.yml
  468  cat http.yml
  469  cat index.html
  470  clear
  471  vi factset.yml
  472  ansible-playbook -i inv  factset.yml
  473  ansible-playbook -i inv  factset.yml -vvv
  474  clear
  475  cat factset.yml
  476  vi factset.yml
  477  ansible-playbook -i inv  factset.yml
  478  vi factset.yml
  479  ansible-playbook -i inv  factset.yml
  480  vi factset.yml
  481  ansible-playbook -i inv  factset.yml
  482  vi factset.yml
  483  ansible-playbook -i inv  factset.yml
  484  ansible demo -a "yum remove ntp -y " -i inv
  485  clear
  486  ansible-playbook -i inv  factset.yml
  487  cat factset.yml



===================================================================================

```
```

---
- hosts: all
  vars:
    pkg: ntp
    svc: ntpd
  tasks:
  - name: package installation - {{ pkg }}
    package: name={{ pkg }} state=present
    register: pkg_out
  - name: print installation summ
    debug: var=pkg_out.rc
  - name: ntp file config
    copy: src=ntp.conf dest=/etc/ntp.conf
    notify:
    - restartntp
  - name: to start the svc of {{ pkg }}
    service: name={{ svc }} state=started enabled=yes
  - name: final statement task
    debug: msg="playbook ran successfully , congrats !! on server {{ ansible_hostname }}"
  handlers:
  - name: restartntp
    service: name={{ svc }} state=restarted


========================================================


playbook :
  play
     1
2
3  ---
4
4 ----
5
5


---
- hosts: all
  tasks:
  - name: this is first task
    command: /bin/date12
    ignore_errors: yes
  - name: second task
    service: name=ntpd state=restarted





---
- hosts: all
  vars:
    pkg: ntp
    svc: ntpd
  tasks:
  - name: task1
#    command: /dev/null
    command: ls
    ignore_errors: yes
    register: task1_result
  - name: debug task1
    debug: var=task1_result
  - name: package installation - {{ pkg }}
    package: name={{ pkg }} state=present
    register: pkg_out
  - name: print installation summ
    debug: var=pkg_out.rc
  - name: ntp file config
    copy: src=ntp.conf dest=/etc/ntp.conf
    notify:
    - restartntp
  - name: to start the svc of {{ pkg }}
    service: name={{ svc }} state=started enabled=yes
  - name: final statement task
    debug: msg="playbook ran successfully , congrats !! on server {{ ansible_hostname }}"
  - name: final task
    debug: msg="this task will only run when task1 fails"
    when: task1_result.failed
  handlers:
  - name: restartntp
    service: name={{ svc }} state=restarted



====================================================================================================

"ansible_distribution": "CentOS"

ansible_distribution_major_version 7

"ansible_distribution_version 7.9




[root@main raman]# cat ignore2.yml
- name: Conditional checks
  hosts: all
  tasks:
    - name: Installing web packages on all centos version 7 servers
#      yum: name=httpd state=installed
#      when: ansible_distribution == 'CentOS' and ansible_distribution_major_version == '7'
      when: ansible_distribution == 'CentOS' or ansible_distribution_major_version == '8'
      yum: name=httpd state=installed




# dont try
- name: "shut down CentOS 6 and Debian 7 systems"
    command: /sbin/shutdown -t now
    when: (ansible_facts['distribution'] == "CentOS" and ansible_facts['distribution_major_version'] == "6") or
          (ansible_facts['distribution'] == "Debian" and ansible_facts['distribution_major_version'] == "7")
#





[root@main raman]# cat condition.yml
- hosts: all
  vars:
    key: home
  tasks:
  - name: Register a variable
    package: name=ntp state=installed
    register: ntp_out
    ignore_errors: true
  - name: debug
    debug:
      var: ntp_out
  - name: Use the variable in conditional statement
    shell: echo "motd contains the word ansible"
    when: ntp_out.rc == 0
    register: echo_output

  - name: Display echoed message
    debug:
      var: echo_output.stdout

  - name: Register a variable
    shell: cat /etc/motd
    register: motd_contents

  - name: Use the variable in conditional statement
    shell: echo "motd contains the word {{ key }}"
    when: motd_contents.stdout.find('{{ key }}') != -1
    register: echo_output

  - name: Display echoed message
    debug:
      var: echo_output.stdout



playbook 2:
[root@gagan-master ~]# cat first.yaml
---
- name: play1 for creating user on gagan-client machine
  hosts: gagan-client

  tasks:
    - name: description for task1 for creating user
      user: name=gagandeep state=present
      when: ansible_distribution == "CentOS" and ansible_distribution_version == "7.9"
      register: user_out

    - name: false task
      debug:
        #msg="Print this msg only if user creation is successfull"
        var: user_out
      ignore_errors: true
#      when: user_out.rc == 0

    - name: creating a file on next machine
      file:
        path: /tmp/gds
        state: touch
        mode: 1600
      when: ansible_distribution == "Redhat"


===============================================================================


[ apple, banana, mango , fruit5 . fruit ] =list

operation 

for i in list:
  operation
    



[root@main raman]# cat loop.yml
---
- hosts: all
  tasks:
  - name: add several users
    user:
      name: "{{ item }}"
      state: present
      groups: "wheel"
#    loop: [testuser1,testuser1,testuser1]
    loop:
    - testuser1
    - testuser2
    - testuser3
  - name: second task  for loop with condition
    command: echo {{ item }}
    loop: [1,2,3,5,7,8,9,10]
    when: item>5




CentOS Linux studout





[root@main raman]# cat loop2.yml
---
- hosts: demo
#  gather_facts: false
  gather_facts: true
  tasks:
  - name: check centos version
    command: cat /etc/os-release
    register: centos_version

  - name: output
    debug: var=centos_version

  - name: install packages
    package: name="{{ item }}" state=present
    loop: [php,gcc,talk,vim,httpd]
#    when: ansible_distribution=='CentOS' and ansible_distribution_version=='7.9'
    when: centos_version.stdout.find('CentOS Linux') != -1











```


```






---
- hosts: all
  vars:
    pkg: ntp
    svc: ntpd
  tasks:
  - name: task1
#    command: /dev/null
    command: ls
    ignore_errors: yes
    register: task1_result
  - name: debug task1
    debug: var=task1_result
  - name: package installation - {{ pkg }}
    package: name={{ pkg }} state=present
    register: pkg_out
  - name: print installation summ
    debug: var=pkg_out.rc
    when: pkg_out.rc == 0
  - name: ntp file config
    copy: src=ntp.conf dest=/etc/ntp.conf
    notify:
    - restartntp
  - name: to start the svc of {{ pkg }}
    service: name={{ svc }} state=started enabled=yes
  - name: final statement task
    debug: msg="playbook ran successfully , congrats !! on server {{ ansible_hostname }}"
  - name: final task
    debug: msg="this task will only run when task1 fails"
    when: task1_result.failed
  handlers:
  - name: restartntp
    service: name={{ svc }} state=restarted
===================================================================================================








READ-CSV MODULE :

- hosts: demo
  connection: ssh
  user: root
  become: true
  vars:
    source_file: "/root/yousuf/day4/user_data.csv"  # control node path
    destination_dir: "/tmp"  # Temporary directory on managed nodes
  
  tasks:

  - name: Fetch CSV file from control node to managed nodes
    fetch:
      src: "{{ source_file }}"
      dest: "{{ destination_dir }}"
      flat: yes

  - name: Read a CSV file on managed nodes
    read_csv:
      path: "{{ destination_dir }}/user_data.csv"
      delimiter: ","
    register: usersList

  - name: Create users in loop
    loop: "{{ usersList.results }}"
    user:
      name: "{{ item.user }}"
      uid: "{{ item.uid }}"







- hosts: demo
  connection: ssh
  user: root
  become: true
  vars:
 
  tasks:
 
  - name: Read a CSV file
    read_csv: path=/root/yousuf/day4/user_data.csv delimiter=","
    register: usersList
 
  - name: Create users in loop
    loop: "{{ usersList.results }}"
    user: name="{{ item.user }}" uid="{{ item.uid }}"



==============================================================













---
#- hosts: demo
#  roles:
#  - ramanrole
#  - ntp-role
 
- hosts: demo
  tasks:
    - name: Execute ntp-role
      include_role:
        name: ntp-role
      ignore_errors: true
      register: ntp_result
 
    - name: Execute ramanrole
      when: ntp_result is succeeded
      include_role:
        name: ramanrole





---
- hosts: all
  name: webserver deployment
  vars:
    pkg: httpd
  tasks:
  - name: installing {{ pkg }}
    yum: name={{ pkg }} state=present
  - name: change port of webserver
    lineinfile: path=/etc/httpd/conf/httpd.conf regexp="Listen 80" line="Listen 81"
  - name: configure the config files
    template: src=index.html dest=/var/www/html/index.html
#    copy:
#      dest: /var/www/html/index.html
#      content: "<h1>This is a Raman's apache webserver</h1>"
    notify: restart httpd
  - name: service-start
    service: name=httpd enabled=yes state=started
  handlers:
  - name: restart httpd
    service: name=httpd state=restarted







==================================================================================






[5:38 PM] Raman Khanna
https://old-galaxy.ansible.com/search?deprecated=false&keywords=&order_by=-relevance
Ansible Galaxy
Jump start your automation project with great content from the Ansible community
[5:39 PM] 
Zarkar, Sheetal no longer has access to the chat.

[5:39 PM] Raman Khanna
try to observer galaxy 
[5:40 PM] Raman Khanna
to upload : upload ur role files to ur github repo ; go to ansible galaxy >> my content >> upload ur role github repo...
[5:40 PM] Raman Khanna
Raman Khanna
to upload : upload ur role files to ur github repo ; go to ansible galaxy >> my content >> upload ur role github repo...

old way

[5:41 PM] Raman Khanna
https://galaxy.ansible.com/
Ansible Galaxy
[5:41 PM] Raman Khanna
https://beta-galaxy.ansible.com/
Ansible Galaxy




=============================================================================
pki

systtem password (raman) - source - encrypt>> rsa,aes,xyz --asymmetric key   ----------------------------namar---------------------------------     webserver /login  -dest -decrypt -assymtric



ansible encrypt :

 

ansible-vault -h
  984  clear
  985  ls
  986  ansible-vault encrypt loop.yml
  987  cat loop.yml
  988  ansible-playbook loop.yml -i inv
  989  ansible-playbook loop.yml -i inv --ask-vault-pass
  990  ansible-vault decrypt loop.yml
  991  cat loop.yml
  992  clear
  993  ansible-vault encrypt loop.yml
  994  ls
  995  ansible-vault -h
  996  ansible-vault create new-playb.yml
  997  ls
  998  cat new-playb.yml
  999  ansible-vault view loop.yml
 1000  ansible-vault edit loop.yml
 1001  ansible-vault -h
 1002  clear
 1003  history
 1004  ls
 1005  cd roles
 1006  ls
 1007  ansible-vault encrypt --vault-id password1@prompt ./inv
 1008  ansible-playbook -i inv myplay.yml
 1009  clear
 1010  ansible-vault encrypt --vault-id password2@prompt myplay.yml
 1011  ansible-playbook -i inv myplay.yml
 1012  ansible-playbook -i inv myplay.yml --vault-id password1@prompt password2@prompt
 1013  ansible-playbook -i inv myplay.yml --vault-id password1@prompt --vault-id password2@prompt
 1014  histoy
 1015  history
 1016  ansible-vault encrypt --vault-id password1@prompt ./inv
 1017  ansible-vault encrypt --vault-id password1@prompt inv
 1018  ansible-vault rekey --vault-id password1@prompt inv


=================================================================================


```


```



[root@main raman]# cat http.yml
---
- hosts: all
  name: webserver deployment
  vars:
    pkg: httpd
  tasks:
  - name: installing {{ pkg }}
    yum: name={{ pkg }} state=present
  - name: change port of webserver
    lineinfile: path=/etc/httpd/conf/httpd.conf regexp="Listen 80" line="Listen 81"
  - name: configure the config files
    template: src=index.j2 dest=/var/www/html/index.html
#    copy:
#      dest: /var/www/html/index.html
#      content: "<h1>This is a Raman's apache webserver</h1>"
    notify: restart httpd
  - name: service-start
    service: name=httpd enabled=yes state=started
  handlers:
  - name: restart httpd
    service: name=httpd state=restarted




[root@main raman]# cat index.j2
<html>
  <head>
    <title>Server Information</title>
  </head>
  <body>
    <h1>Raman’s server hosted on {{ ansible_hostname }} having private ip : {{ ansible_all_ipv4_addresses }} and linux-distro : {{ ansible_distribution }} </h1>
</body>
</html>







[root@main raman]# cat jinja.yml
---
- hosts: all
  tasks:
  - name: execute command
    command: echo 'hello capgemini users'
    register: my_comm_output
#  - name: temp
#    debug: var=my_comm_output
  - name: set a fact based on regsitered var
    set_fact:
      rk: "{{ my_comm_output.stdout }}"
  - name: coping the motd file on remote srvers
    template: src=/root/raman/motd.j2 dest=/etc/motd



[root@main raman]# cat motd.j2
********************** welcome 2 {{ ansible_distribution }} server ; {{ rk }} **************************
IP add of this server is  {{ ansible_default_ipv4.address }}
this hostname is {{ ansible_fqdn }}


--------------------------------------------------------

group of tasks : .yml

- name: execute command
    command: echo 'hello capgemini users'
    register: my_comm_output
#  - name: temp
#    debug: var=my_comm_output
  - name: set a fact based on regsitered var
    set_fact:
      rk: "{{ my_comm_output.stdout }}"

========================================================================

--- block run:
   tasks 1
    2 
    3
    4
   when:
   ignore err

-  2md


tags :

1,3 prod

1,2,4 dev



ansible-playbook -i inv http.yml --tags prod
1077  vi http.yml
1078  ansible-playbook -i inv http.yml --tags prod
1079  vi http.yml
1080  ansible-playbook -i inv http.yml --tags prod
1081  ansible-playbook -i inv http.yml --tags dev
1082  ansible-playbook -i inv http.yml --tags dev,prod
1083  ansible-playbook -i inv http.yml --skip-tags prod

[root@main raman]# cat http.yml --- - hosts... by Raman Khanna
4:26 PM
Raman Khanna
[root@main raman]# cat http.yml
---
- hosts: all
  name: webserver deployment
  vars:
    pkg: httpd
  tasks:
  - include_tasks: task_group.yml
  - name: 1 installing {{ pkg }}
    yum: name={{ pkg }} state=present
    ignore_errors: true
    tags:
    - prod
    - dev
  - name: 2 change port of webserver
    lineinfile: path=/etc/httpd/conf/httpd.conf regexp="Listen 80" line="Listen 81"
    ignore_errors: true
    tags:
    - dev
  - name: 3 configure the config files
    template: src=index.j2 dest=/var/www/html/index.html
#    copy:
#      dest: /var/www/html/index.html
#      content: "<h1>This is a Raman's apache webserver</h1>"
    notify: restart httpd
    ignore_errors: true
    tags:
    - prod
  - name: 4 service-start
    service: name=httpd enabled=yes state=started
    ignore_errors: true
    tags:
    - dev
  handlers:
  - name: restart httpd
    service: name=httpd state=restarted
 
has context menu


======================================================


tasks:
   - name: Install, configure, and start Apache
     block:
       - name: Install httpd and memcached
         yum:
           name:
           - httpd
           - memcached
           state: present

       - name: Apply the foo config template
           template:
           src: templates/src.j2
           dest: /etc/foo.conf

       - name: Start service bar and enable it
         service:
           name: bar
           state: started
           enabled: True
     when: ansible_facts['distribution'] == 'CentOS'
     become: true
     become_user: root
     ignore_errors: yes
   - name: install ntp 
     block: 


=================================================================
ansible-playbook --tags xyz
vi http.yaml
include_tasks: tasks.yml , import_tasks : (tasks.yml 4)



identation is diff than 
- import_playbook : 


aws roles /aws configure:

iam permissions:

iam roles : bots/service accounts /aws applicationsitself




[root@main raman]# cat ec2.yml
---
- name: Create EC2 instance
  hosts: localhost
  gather_facts: False
  vars:
    ansible_python_interpreter: /usr/bin/python3
  tasks:
    - name: Launch EC2 instance
      ec2:
        key_name: raman-nvirgnia
        instance_type: t2.micro
        image: ami-002070d43b0a4f171
        region: us-east-1
        group: raman-sg
        count: 1
        wait: yes
        instance_tags: '{"Name":"Ansible-raman-ec2-KSA-2"}'
      register: ec2_instance
    - name: Display registered variable
      debug:
        var: ec2_instance




ansible-playbook ec2.yml
 1163  python --version
 1164  ansible --vesion
 1165  ansible --version
 1166  clear
 1167  yum install boto
 1168  pip
 1169  yum install python3
 1170  pip3
 1171  clear
 1172  pip3 install boto
 1173  yum install boto3
 1174  ansible-playbook ec2.yml
 1175  ansible --version
 1176  ls
 1177  vi ec2.yml
 1178  ansible-playbook ec2.yml
 1179  vi ec2.yml
 1180  ansible-playbook ec2.yml
 1181  vi ec2.yml
 1182  ansible-playbook ec2.yml

======================================================================

```


```

include_tasks , import tasks

commontasks.yml
- task1
- task 2
  tags : dev
- tasks 3
- tasks 4
  tasgs: dev

--------------------------------------------


import_playbook







raman.yaml                                           ,,, khanna.yml : another playbook    1: other,2,3other ,4,5 other
---
- hosts: all
  name: 1st play
  tasks:
  - create a file 
  - include_tasks: commontasks.yml
- import_playbook: khanna.yml





ansible-playbook --tags other,dev


-------------------------------

aws configure /aws role


az login




sudo -i
yum update -y
yum install -y unzip
yum install -y wget
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#cliv2-linux-install (copy the three commands)
ln -s  /usr/local/bin/aws  /usr/bin/
aws --version --To get the version of aws 





-----------------------------------------------------


"  host1    2    3   4   5  "   6  7 

task1
task2 
task3




host1
hst2
3
4
5
6
5

=======================================================================

main ------------------ ssh ------------------------------- mnged nodes linux

main (linux)  ---------   winrm  ------------------------------ mngedn nodes win


windows server : local windpws laptop :   --------------- rdp ( 3389 ) --------------- windows server

Microsoft Windows Server 2019 with Desktop Experience Locale English AMI provided by Amazon
ami-02093b660fa33729e


Software Image (AMI)
Microsoft Windows Server 2019 ...read more
ami-02093b660fa33729e
Virtual server type (instance type)
t2.medium
Firewall (security group)
raman-sg
Storage (volumes)
1 volume(s) - 30 GiB



QKZ)NmYJ?-OW7UPpbbL2s7auBrKYugSx



----------------------------------------------------------


pywinrm : pip3 : python 3 




asible --version
 1106  ansible --version
 1107  python --version
 1108  alternatives --set python /usr/bin/python3
 1109  alternatives --install /usr/bin/python python /usr/bin/python3 1
 1110  cd /var/lib/alternatives/
 1111  ls
 1112  alternatives --set python
 1113  alternatives --set python /usr/bin/python3
 1114  ls
 1115  python
 1116  clear
 1117  python --version
 1118  ansible --version




python --version
 1118  ansible --version
 1119  clear
 1120  history
 1121  cd /root/raman/
 1122  ls
 1123  pip3 install virtualenv
 1124  python -m virtualenv env
 1125  ls
 1126  source env/bin/activate
 1127  python --version
 1128  python -m pip install --upgrade
 1129  python3 -m pip install --upgrade
 1130  python -m pip install --upgrade pip
 1131  pip3 install ansible
 1132  pip3 install pywinrm
 1133  ansible --version



================================================================

```
