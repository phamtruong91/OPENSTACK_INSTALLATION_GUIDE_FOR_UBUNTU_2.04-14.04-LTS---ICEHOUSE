OPENSTACK
=================================================================
#Cài đặt OpenStack ICEHOUSE trên 3 Node

Nguồn: http://docs.openstack.org/icehouse/install-guide/install/apt/content/index.html

##Cài đặt OpenStack ICEHOUSE trên node Controller

* KeyStone
* Glance
* Nova

1. Chuẩn bị

* IP 

|       HOST      |     NICS                |
| --------------- | ----------------------- | 
|    Controller   | eth0: 10.10.10.100/24   |
|                 | eth1: 10.145.48.100/24  | 

* Cấu hình máy

Controller: 

* HDD: 20 GB
* CPU: 02 (Có tích vào các chế độ ảo hóa)
* RAM: 2GB 
* NIC: 02 NICs (eth0 - chế độ vmnet2 ), (eth1 - chế độ brige)

* Hệ điều hành Ubuntu Server 12.04

1.  Cấu hình cơ bản


