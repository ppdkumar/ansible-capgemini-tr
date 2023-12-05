```
practise server :


main pr : 3.94.208.216

m1: 54.205.248.254

m2: 23.22.118.142

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
