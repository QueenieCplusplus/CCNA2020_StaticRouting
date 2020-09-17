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
           
