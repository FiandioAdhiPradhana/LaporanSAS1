**LAPORAN SAS** 

 

Pastikan adaptop bridge dan setting ip static

![image](https://user-images.githubusercontent.com/93086665/138603980-77f04753-489c-4ac3-9368-27eb1b3a84a4.png)

Cek lxc yang sudah ada di praktikum sebelumnya 

![image](https://user-images.githubusercontent.com/93086665/138603989-a0159107-5a9f-431e-89d5-ac16d855f03a.png)


NOMOR 1

Ubah Ubuntu 5.6 menjadi Ubuntu landing

![image](https://user-images.githubusercontent.com/93086665/138604002-c54c644d-205a-40af-b3bf-bc6c9e1db407.png)
 

Start lxc php landing dan php 7

![image](https://user-images.githubusercontent.com/93086665/138604007-320c4ac2-cace-4d57-93fe-a5a3992f30d3.png)

 

Masuk ke Ubuntu landing

![image](https://user-images.githubusercontent.com/93086665/138604013-6a508f2d-7600-487c-bfe8-ddebbb793013.png)

Ubah ip Ubuntu landing

![image](https://user-images.githubusercontent.com/93086665/138604017-60069aba-cd2c-4997-96fd-3c5c5f15a215.png)


 

Restart ip lalu cek ip menggunakan ifconfig

![image](https://user-images.githubusercontent.com/93086665/138604021-5c3b80b1-5f57-4ab4-ab2f-3013403b47ed.png)

 

Keluar dari Ubuntu landing

![image](https://user-images.githubusercontent.com/93086665/138604031-21ca1073-3b31-4f69-a47d-f1c231246250.png)

 

NOMOR 2

Cek koneksi internet dengan ping google.com / 8.8.8.8/ 1.1.1.1

![image](https://user-images.githubusercontent.com/93086665/138604039-81c26cba-337f-4d26-a475-576c24506bb9.png)

Update respositori debian di nano /etc/apt.sources.list

![image](https://user-images.githubusercontent.com/93086665/138604042-6bae1769-f99f-422a-a8d0-9cfeae336ad4.png)

Install lxc debian

 ![image](https://user-images.githubusercontent.com/93086665/138604047-92e8bcf0-d0cd-4561-a5b4-b8dfc8a94c67.png)


Cek lcx debian

![image](https://user-images.githubusercontent.com/93086665/138604049-a0dfc2c5-0e0d-46b7-ad6b-32ebf7898cc8.png)

Nomor 3 

Start lxc debian 

![image](https://user-images.githubusercontent.com/93086665/138604053-f55af356-5125-4f43-8ff3-8abc771e7248.png)

Install nginx dan nginx-extras

![image](https://user-images.githubusercontent.com/93086665/138604054-fbc59ba2-41cd-4c7b-8475-1d615a376e4d.png)

Install nano dan net-tools dan curl

![image](https://user-images.githubusercontent.com/93086665/138604061-d1992fe5-681b-4932-8462-505917b36ac1.png)

 

Setting ip static debian php

 ![image](https://user-images.githubusercontent.com/93086665/138604063-29e547cf-ebfd-43dd-96b5-8b41effc07b2.png)

 
Restrart pengaturan dan cek ip

![image](https://user-images.githubusercontent.com/93086665/138604076-dbda8d2c-fee7-48e4-8aa1-fb5afd1bd89a.png)

Setting nginx

![image](https://user-images.githubusercontent.com/93086665/138604081-b7c15c8e-3268-4a1b-9d08-47069b540fa7.png)

![image](https://user-images.githubusercontent.com/93086665/138604085-ec56fa75-f94e-45e2-8814-44e521bca336.png)

![image](https://user-images.githubusercontent.com/93086665/138604088-ba0686d5-cdb4-4290-9916-09ec92f48bb1.png)
 
![image](https://user-images.githubusercontent.com/93086665/138604092-8426aa3c-4089-4f19-8b2a-0c5392265516.png)

![image](https://user-images.githubusercontent.com/93086665/138604096-2871e04f-aa50-4747-82c9-a5d71f2c7d13.png)
 
![image](https://user-images.githubusercontent.com/93086665/138604100-46fbb83b-0e75-41a6-a002-48c961154e63.png)


Test dengan curl

![image](https://user-images.githubusercontent.com/93086665/138604108-71af9d12-b8fd-4a76-8e86-0304bf2ce8d9.png)

Exit dari debian php

 

NOMER 4

Masuk Ubuntu landing dan setting nginx

![image](https://user-images.githubusercontent.com/93086665/138604113-89b8bfda-859b-421b-bb4a-c098dc7a339d.png)

![image](https://user-images.githubusercontent.com/93086665/138604117-fe93e300-2e40-4fd4-af54-4a498a3e825a.png)

![image](https://user-images.githubusercontent.com/93086665/138604119-a6e2a528-6057-42ad-8948-1132e44f0ee4.png)

![image](https://user-images.githubusercontent.com/93086665/138604122-dd700c0c-1122-4d4d-99e0-d332e5f3fdcb.png)

![image](https://user-images.githubusercontent.com/93086665/138604126-0499a64b-06c3-4703-9025-dff381d0670a.png)

![image](https://user-images.githubusercontent.com/93086665/138604128-62ee5834-3e70-44e8-b6ca-2d984b9e9a2f.png)
 

Test dengan curl

![image](https://user-images.githubusercontent.com/93086665/138604132-be6d702e-87c2-473c-94d3-d96055c17103.png)

Exit Ubuntu landing

NOMER 5

Stop Ubuntu landing dan cek

![image](https://user-images.githubusercontent.com/93086665/138604137-e2f19460-879c-488d-8cc8-20e25b429d9b.png)

 

Masuk ke direktori/ var/ lib/lxc dan cek ada direktori apa aja

![image](https://user-images.githubusercontent.com/93086665/138604139-139a6306-522d-4120-94fd-a63aa93bf9ba.png)

Karena akan menggunakan auto start pada Ubuntu landing, maka tambahkan config seperti dibawah

![image](https://user-images.githubusercontent.com/93086665/138604142-5c4952c3-8709-4c14-a89d-019a2d899939.png)

Cek auto start dengan cara reboot dahulu

NOMER 6

Setup nginx pada vm local

![image](https://user-images.githubusercontent.com/93086665/138604146-f8a2a39c-4503-4c0e-975d-c4f28e22c5c2.png)

![image](https://user-images.githubusercontent.com/93086665/138604151-6c5dd80e-f19d-4bc1-8007-189ad3994c9b.png)

![image](https://user-images.githubusercontent.com/93086665/138604154-0209e212-e2af-44a1-8643-b0056c2eb34f.png)

![image](https://user-images.githubusercontent.com/93086665/138604156-9994daf4-5221-47bb-87bc-3aa427908754.png)

![image](https://user-images.githubusercontent.com/93086665/138604157-3fcd23b1-67c8-44bf-9bb0-130836e46d6e.png)

![image](https://user-images.githubusercontent.com/93086665/138604160-7cbe75ee-24af-4f37-9d5c-db3e3fe8dc11.png)

![image](https://user-images.githubusercontent.com/93086665/138604162-b65b2355-d4e6-4cb5-a044-a9c00e423368.png)

![image](https://user-images.githubusercontent.com/93086665/138604164-366a5dc7-5c37-4d8d-99a2-702820b08689.png)

![image](https://user-images.githubusercontent.com/93086665/138604167-945cf7b2-882c-4409-850c-e10fc655173c.png) 

![image](https://user-images.githubusercontent.com/93086665/138604170-0520ca99-5212-4f4d-aceb-47647f0e0cbc.png)

![image](https://user-images.githubusercontent.com/93086665/138604173-0e0eec8e-3842-4479-a777-1cb6ad065202.png)
