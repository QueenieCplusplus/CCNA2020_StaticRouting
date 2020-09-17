# CCNA2020_StaticRouting
靜態路由

是一種路由方式，由網路管理員手動操作路由表，將路由項 routing entry 輸入至路由表中。

# 架構圖範例

IP 的位址與子遮罩都攸關流量控制（分流）。



                         Internet
                         
                             |
                             |
                             |
                             
                             
                           Router    -----------      SW   ----------   workstations
                       192.168.1.254 (private ip)
                            
                              
                             |
                             |
                             |
                             
                           Router
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
                    
                 |            |           |
                PC 1         PC2          PC3
              
        192.168.100.24      192.168.100.3    192.168.100.4             
                             
                     192.168.100.1 (default GW)
