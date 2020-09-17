# CCNA2020_StaticRouting
靜態路由

是一種路由方式，由網路管理員手動操作路由表，將路由項 routing entry 輸入至路由表中。

# 架構圖範例

IP 的位址與子遮罩都攸關流量控制（分流）。



                         Internet （WAN）
                         
                             |
                             |
                             |
                           
                           (LAN)
                           
                             |
                             |
                             |
                           
                             
                           Router 1   -----------      SW   ----------   workstations
                       192.168.1.254 (private ip)
                        NAT (public ip)
                            
                              
                             |
                             |
                             |
                             
                             
                         (Protected LAN)
                           
                             
                             |
                             |
                             |
                             
                           Router 2
                       192.168.1.100 (public ip)
                       192.168.1.254 (default gW)
                       192.168.100.1 (private ip)
                       
                       
                             |
                             |
                             |
                             
                             
                            SW
                       
                            
                             |
                             |
                             |
                             
                    Group of Workstations
                    
                  |              |              |
               My PC(admin)   Mail Server    Web Server
              
        192.168.100.24    192.168.100.3   192.168.100.4             
                             
                     192.168.100.1 (default GW)

# 發送回應和接收請求


receive request

           Web Server   <-----------   Router 2    <-----------   Router 1  <-----------  Internet
          192.168.100.4               192.168.100.1              192.168.1.254
          192.168.100.1               192.168.1.254                  NAT


send response

            Web Server  ----------->   Router 2    ----------->   Router 1  ----------->  Internet
          192.168.100.4               192.168.100.1              192.168.1.254
          192.168.100.1               192.168.1.254                  NAT
           

# 靜態路由的設定


My PC (admin)

    IP: 192.168.100.24
    netmask: 255.255.255.0
    gateway: 192.168.100.1
    hostname: clientlinux.centos.PkateQ
    DNS: 168.95.1.1 (等待確認)
    
    
Router 2 (受保護內網的路由器)

兩張 NIC

    eth0: 192.168.1.100/24 (public ip)
    eth1: 192.168.100.1/24 (private ip)


Router 1 (連接外網與內網的路由器)

兩張 NIC

對外的網卡 > 設定在 eth1 介面
而對內部的 > 設定在 eth0 介面 > 192.168.1.254 
