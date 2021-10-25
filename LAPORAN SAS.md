# Lab Report 1 System Admintration Server
# Practicum Module 1 Virtualisasi - Sistem Administrasi Server

**From Group 11**

**Reksa Aldian Rahmandy Putra 1202192048 || Fiandio Adhi Pradana 1202192034**

---------
**Case Study**
------
Create an basic virtualization as a company profile website based on domain strategy that has explain by CTO.

- vm.local
  - Containing Landing Page
- vm.local/blog
  - Containing Blog
- vm.local/app
  - Containing Enterprise App

 ![soal](https://user-images.githubusercontent.com/93086665/138634860-c53ad52b-3193-44d0-b20c-ede41959a843.png)

| Server Name                    | IP         | Domain                 |
| ------------------------------ | ---------- | ---------------------- |
| LXC ubuntu server 18.04 php7.4 | 10.0.3.101 | http://lxc_php7.dev    |
| LXC debian server 9 php5.6     | 10.0.3.102 | http://lxc_php5.dev    |
| LXC ubuntu server 16.04        | 10.0.3.103 | http://lxc_landing.dev |

Make sure about bridge adaptor and Ip static setting

![image](https://user-images.githubusercontent.com/93086665/138603980-77f04753-489c-4ac3-9368-27eb1b3a84a4.png)

Check the lxc that has been in the previous practicum 

![image](https://user-images.githubusercontent.com/93086665/138603989-a0159107-5a9f-431e-89d5-ac16d855f03a.png)

*Log in to super user with using command `sudo su`*

**1. Rename ubuntu_php5.6 to ubuntu_landing, also change the IP following the new scheme**

   Type
   ```
   lxc-copy -R -n ubuntu_php5.6 -N ubuntu_landing
   ```
   
Change Ubuntu 5.6 into Ubuntu landing

![image](https://user-images.githubusercontent.com/93086665/138604002-c54c644d-205a-40af-b3bf-bc6c9e1db407.png)
 
 To make sure the name of ubuntu_php5.6 has changed, we can check using the command
   ```
   lxc-ls -f
   ```
   
Start lxc php landing and php 7

![image](https://user-images.githubusercontent.com/93086665/138604007-320c4ac2-cace-4d57-93fe-a5a3992f30d3.png)

If the container name has changed to ubuntu_landing, we have to change the IP from before to a new one following the new scheme
We need to start the container first (Ubuntu_landing and ubuntu_php7.4)
   ```
   lxc-start -n ubuntu_landing
   lxc-start -n ubuntu_php7.4
   ```

Enter into Ubuntu landing

![image](https://user-images.githubusercontent.com/93086665/138604013-6a508f2d-7600-487c-bfe8-ddebbb793013.png)

after that go to ubuntu landing
   ```
   lxc-attach -n ubuntu_landing
   ```

Change ip Ubuntu landing

![image](https://user-images.githubusercontent.com/93086665/138604017-60069aba-cd2c-4997-96fd-3c5c5f15a215.png)

After we enter the root, we need to set the IP following the new scheme
   ```
   nano /etc/network/interfaces
   ```
![WhatsApp Image 2021-10-25 at 12 43 33](https://user-images.githubusercontent.com/93086665/138646762-c76b7e0b-5ef6-4d2d-b558-009633acd774.jpeg)


Restart ip then check ip with ifconfig

  then restart ip `systemctl restart networking.service`. and check ip using `ifconfig`
![image](https://user-images.githubusercontent.com/93086665/138604021-5c3b80b1-5f57-4ab4-ab2f-3013403b47ed.png)


Exit from Ubuntu landing

![image](https://user-images.githubusercontent.com/93086665/138604031-21ca1073-3b31-4f69-a47d-f1c231246250.png)

 
2. Install LXC Debian 9 with the name ubuntu_php5.6
type

Check connection internet with ping google.com / 8.8.8.8/ 1.1.1.1

```
with ping 8.8.8.8 or 1.1.1.1
```

![image](https://user-images.githubusercontent.com/93086665/138604039-81c26cba-337f-4d26-a475-576c24506bb9.png)

Update respositori debian first

```
You can update in nano /etc/apt.sources.list
```

![image](https://user-images.githubusercontent.com/93086665/138604042-6bae1769-f99f-422a-a8d0-9cfeae336ad4.png)

Install lxc debian
```
 sudo lxc-create -n debian_php5.6 -t download -- --dist debian --release stretch --arch amd64 --force-cache --no-validate --server images.linuxcontainers.org
   ```
 ![image](https://user-images.githubusercontent.com/93086665/138604047-92e8bcf0-d0cd-4561-a5b4-b8dfc8a94c67.png)

Check LXC Debian Again

```
Check debian with command lxc-ls -f
```

![image](https://user-images.githubusercontent.com/93086665/138604049-a0dfc2c5-0e0d-46b7-ad6b-32ebf7898cc8.png)

3. Setup debian_php5.6 nginx to it's domain `http://lxc_php5.dev`, then make index.html page that explains lxc names information
Start debian_php5.6 
   ```
   lxc-start -n debian_php5.6
   lxc-ls -f 
   lxc-attach -n debian_php5.6
   ```

![image](https://user-images.githubusercontent.com/93086665/138604053-f55af356-5125-4f43-8ff3-8abc771e7248.png)

Then Install nginx and nginx-extras
```
   apt install nginx nginx-extras
   ```

![image](https://user-images.githubusercontent.com/93086665/138604054-fbc59ba2-41cd-4c7b-8475-1d615a376e4d.png)

Then Install net tools 
```
apt install nano net-tools curl
```

![image](https://user-images.githubusercontent.com/93086665/138604061-d1992fe5-681b-4932-8462-505917b36ac1.png)

 Afterthat Setting ip static debian_php5.6
   ```
   nano /etc/network/interfaces
   ```
 ![image](https://user-images.githubusercontent.com/93086665/138604063-29e547cf-ebfd-43dd-96b5-8b41effc07b2.png)

 
Restart Setting of ip and check the ip
```
then restart ip `systemctl restart networking.service`. and check ip using `ifconfig`
```
![image](https://user-images.githubusercontent.com/93086665/138604076-dbda8d2c-fee7-48e4-8aa1-fb5afd1bd89a.png)

Next setting nginx 
After that we need to set the nginx with command
```
cd /etc/nginx/sites-avaliable for open the directory and then we can see the directory with "ls"
```

![image](https://user-images.githubusercontent.com/93086665/138604081-b7c15c8e-3268-4a1b-9d08-47069b540fa7.png)

then we need to open the container with
```
nano /etc/lxc_php5.6.dev
```

![image](https://user-images.githubusercontent.com/93086665/138604085-ec56fa75-f94e-45e2-8814-44e521bca336.png)


![image](https://user-images.githubusercontent.com/93086665/138604088-ba0686d5-cdb4-4290-9916-09ec92f48bb1.png)

Then we need to configure the hosts
   ```
   nano /etc/hosts
   ```
![image](https://user-images.githubusercontent.com/93086665/138604092-8426aa3c-4089-4f19-8b2a-0c5392265516.png)

After we save it then we need to enter the directory for html
   ```
   cd /var/www/html
   mkdir lxc_php5.6
   cp index.nginx-debian.html lxc_php5.6/index.html
   cd lxc_php5.6
   nano index.html
   ```

![image](https://user-images.githubusercontent.com/93086665/138604096-2871e04f-aa50-4747-82c9-a5d71f2c7d13.png)
 
![image](https://user-images.githubusercontent.com/93086665/138604100-46fbb83b-0e75-41a6-a002-48c961154e63.png)


After that, we need to check if the code that we type in index.html
   ```
   curl -i http://lxc_5.dev
   ```
![image](https://user-images.githubusercontent.com/93086665/138604108-71af9d12-b8fd-4a76-8e86-0304bf2ce8d9.png)

and it works!!!, then exit

4. Setup ubuntu_landing nginx to it's domain `http://lxc_landing.dev`, then make index.html page that explains lxc names information. for the step like no 3

![image](https://user-images.githubusercontent.com/93086665/138604113-89b8bfda-859b-421b-bb4a-c098dc7a339d.png)

![image](https://user-images.githubusercontent.com/93086665/138604117-fe93e300-2e40-4fd4-af54-4a498a3e825a.png)

![image](https://user-images.githubusercontent.com/93086665/138604119-a6e2a528-6057-42ad-8948-1132e44f0ee4.png)

![image](https://user-images.githubusercontent.com/93086665/138604122-dd700c0c-1122-4d4d-99e0-d332e5f3fdcb.png)

Code in index.html just like this

![image](https://user-images.githubusercontent.com/93086665/138604126-0499a64b-06c3-4703-9025-dff381d0670a.png)

![image](https://user-images.githubusercontent.com/93086665/138604128-62ee5834-3e70-44e8-b6ca-2d984b9e9a2f.png)
 

Than check with command curl
   ```
   curl -i http://lxc_landing.dev
   ```

![image](https://user-images.githubusercontent.com/93086665/138604132-be6d702e-87c2-473c-94d3-d96055c17103.png)

Exit Ubuntu landing

5.  LXC ubuntu_landing need to be 'auto start' when we turn on vm. We need to enter super user to enter config page
Go to the /var/lib/lxc directory and check if there are any directories

Stop Ubuntu landing and check the ubuntu landing
```
lxc-stop -n ubuntu_landing
```

![image](https://user-images.githubusercontent.com/93086665/138604137-e2f19460-879c-488d-8cc8-20e25b429d9b.png)

 

Goes to directory and check what about in directory
```
/ var/ lib/lxc
```
![image](https://user-images.githubusercontent.com/93086665/138604139-139a6306-522d-4120-94fd-a63aa93bf9ba.png)

Because it will use auto start on ubuntu landing, add config like below and then Cek auto start with reboot first

![image](https://user-images.githubusercontent.com/93086665/138604142-5c4952c3-8709-4c14-a89d-019a2d899939.png)

6. Setup nginx for vm.local to config the proxy_pass
Setup nginx on local vm
   ```
   sudo nano /etc/hosts
   ```

![image](https://user-images.githubusercontent.com/93086665/138604146-f8a2a39c-4503-4c0e-975d-c4f28e22c5c2.png)

![image](https://user-images.githubusercontent.com/93086665/138604151-6c5dd80e-f19d-4bc1-8007-189ad3994c9b.png)

After that we need to install nginx, then enter the directory of sites available, then enter the nano of vm.local

![image](https://user-images.githubusercontent.com/93086665/138604154-0209e212-e2af-44a1-8643-b0056c2eb34f.png)

Edit the nano vm.local

![image](https://user-images.githubusercontent.com/93086665/138604156-9994daf4-5221-47bb-87bc-3aa427908754.png)

Setting the Ip Vm.local and others in command prompt and go to notepad with administator

![image](https://user-images.githubusercontent.com/93086665/138604157-3fcd23b1-67c8-44bf-9bb0-130836e46d6e.png)

To check the html code appears as it should or not, use the curl command, curl is a command line tool to transfer data to or server, using any of the supported protocols like HTTP, FTP, etc.
 




![image](https://user-images.githubusercontent.com/93086665/138604162-b65b2355-d4e6-4cb5-a044-a9c00e423368.png)



![image](https://user-images.githubusercontent.com/93086665/138604167-945cf7b2-882c-4409-850c-e10fc655173c.png) 



![image](https://user-images.githubusercontent.com/93086665/138604173-0e0eec8e-3842-4479-a777-1cb6ad065202.png)
