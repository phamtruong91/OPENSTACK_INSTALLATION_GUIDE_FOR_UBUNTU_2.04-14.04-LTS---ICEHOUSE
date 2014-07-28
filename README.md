OPENSTACK
=================================================================
#Cài đặt OpenStack ICEHOUSE trên 3 Node

Nguồn: http://docs.openstack.org/icehouse/install-guide/install/apt/content/index.html

##Cài đặt OpenStack ICEHOUSE trên node Controller

* KeyStone
* Glance
* Nova

### 1. Chuẩn bị

* IP 

|       HOST     |          NICS          |
| ---------------|------------------------| 
|    Controller  | eth0: 10.10.10.100/24  |
|                | eth1: 10.145.48.100/24 | 

* Cấu hình máy

Controller: 

* HDD: 20 GB
* CPU: 02 (Có tích vào các chế độ ảo hóa)
* RAM: 2GB 
* NIC: 02 NICs (eth0 - chế độ vmnet2 ), (eth1 - chế độ brige)

* Hệ điều hành Ubuntu Server 12.04

### 2.  Cấu hình cơ bản

* Đặt tên hostname: controller
* Sửa file etc/hosts

```
# controller
10.10.10.100       controller
# network
10.10.10.101       network
# compute1
10.10.10.102       compute1
```

* Network Time Protocol (NTP)

Cài đặt ntp:
```
# apt-get install ntp
```
Để cho phép Network và Compute node đồng bộ thời gian với Controller node, sửa file /etc/ntp.conf

Comment các dòng (thêm dấu #)
```
server 0.ubuntu.pool.ntp.org
server 1.ubuntu.pool.ntp.org
server 2.ubuntu.pool.ntp.org
server 3.ubuntu.pool.ntp.org
```
Sửa dòng server ntp.ubuntu.com thành server 10.10.10.100

Lưu thay đổi và khởi động lại dịch vụ NTP
```
#service ntp restart
```
* Passsword
```
$ openssl rand -hex 10
```
![image](http://prntscr.com/472w9m)
