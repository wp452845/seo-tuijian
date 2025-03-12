# DMIT LAX PRO 产品线路测试报告

今天为大家详细测试 DMIT 的 LAX PRO 产品。LAX PRO 是 DMIT 旗下主力产品，基于自家线路，具有强大的三网回程 CN2 GIA 能力及充足的带宽，近年来在用户体验和稳定性方面表现出色。以下为本次测试的配置及数据详情。

👉 [【推荐收藏】2025年 DMIT 最新优惠活动整理汇总 - 每日更新可用优惠套餐](https://bit.ly/dmit_coupon)

## 测试服务器配置详情

测试服务器来自夏日优惠套餐 PalmSpring，具体配置如下：


vCPU：2C [AMD EPYC 7402P]
RAM：2G
Disk：40G
Bandwidth：2T
Network Port：2Gbps Shared Port
1 ipv4 & 1 ipv6
Snapshot：1 Free Quota


---

## 系统性能测试

### Bench.sh 测试结果

以下为通过 Bench.sh 脚本获取的系统性能数据：


-------------------- A Bench.sh Script By Teddysun -------------------
 Version            : v2023-10-15
 Usage              : wget -qO- bench.sh | bash
----------------------------------------------------------------------
 CPU Model          : AMD EPYC 7402P 24-Core Processor
 CPU Cores          : 2 @ 2794.748 MHz
 CPU Cache          : 512 KB
 AES-NI             : ✓ Enabled
 VM-x/AMD-V         : ✓ Enabled
 Total Disk         : 39.6 GB (8.0 GB Used)
 Total Mem          : 1.9 GB (566.7 MB Used)
 Total Swap         : 1.0 GB (76.4 MB Used)
 System uptime      : 9 days, 11 hour 32 min
 Load average       : 0.00, 0.00, 0.00
 OS                 : Ubuntu 22.04.3 LTS
 Arch               : x86_64 (64 Bit)
 Kernel             : 5.15.0-41-generic
 TCP CC             : bbr
 Virtualization     : Dedicated
 IPv4/IPv6          : ✓ Online / ✓ Online
 Organization       : AS906 DMIT Cloud Services
 Location           : Los Angeles / US
 Region             : California
----------------------------------------------------------------------
 I/O Speed(1st run) : 665 MB/s
 I/O Speed(2nd run) : 713 MB/s
 I/O Speed(3rd run) : 733 MB/s
 I/O Speed(average) : 703.7 MB/s
----------------------------------------------------------------------
 Node Name        Upload Speed      Download Speed      Latency     
 Speedtest.net    1324.10 Mbps      918.81 Mbps         59.94 ms    
 Los Angeles, US  2063.88 Mbps      1949.97 Mbps        0.95 ms     
 Dallas, US       1554.06 Mbps      1900.03 Mbps        36.66 ms    
 Montreal, CA     582.84 Mbps       828.89 Mbps         71.39 ms    
 Paris, FR        569.22 Mbps       1672.33 Mbps        145.42 ms   
 Amsterdam, NL    545.16 Mbps       1668.97 Mbps        150.20 ms   
 Shanghai, CN     627.01 Mbps       1502.37 Mbps        135.45 ms   
 Mumbai, IN       302.00 Mbps       1577.14 Mbps        225.44 ms   
 Singapore, SG    372.98 Mbps       1523.03 Mbps        192.10 ms   
 Tokyo, JP        396.34 Mbps       1677.47 Mbps        101.32 ms   
----------------------------------------------------------------------
 Finished in        : 5 min 0 sec
 Timestamp          : 2023-11-22 13:19:26 UTC
---------------------------------------------------------------------- 


从以上数据可以看出，该服务器在读写性能、基础网络上传下载测速等方面表现更加突出，特别是在国外节点速度上传和整体连接延迟上表现堪优。

---

## Geekbench 5 测试结果

以下为服务器通过 Geekbench 5 压测的详细结果：


系统信息
  Operating System              Ubuntu 22.04.3 LTS
  Kernel                        Linux 5.15.0-41-generic x86_64
  Model                         QEMU Standard PC (Q35 + ICH9, 2009)
  Motherboard                   N/A
  BIOS                          SeaBIOS rel-1.14.0-0-g155821a1990b-prebuilt.qemu.org

处理器信息
  Name                          AMD EPYC 7402P 24-Core Processor               
  Topology                      1 Processor, 2 Cores
  Identifier                    AuthenticAMD Family 23 Model 49 Stepping 0
  Base Frequency                2.79 GHz
  L1 Instruction Cache          64.0 KB x 2
  L1 Data Cache                 64.0 KB x 2
  L2 Cache                      512 KB x 2
  L3 Cache                      16.0 MB

内存信息
  Size                          1.93 GB

单核测试分数：862  
多核测试分数：1664  
详细测试结果链接：[点击查看详细分数](https://browser.geekbench.com/v5/cpu/21972713) 


从测试结果看，该产品 CPU 性能标准优良，在常规多任务处理上也很可靠，同时保证了稳定性。

---

## 全网解锁测试

该产品还对主要多媒体应用进行了解锁能力测试。IPv4 与 IPv6 网络结果如下：

### IPv4 解锁情况

- Disney+：**No**
- Netflix：**Originals Only**
- Amazon Prime Video：**Yes**
- iQiyi：**US**
- Spotify：**No**

### IPv6 解锁情况

- Disney+：**Yes**
- Netflix：**Originals Only**
- Amazon Prime Video：**Unsupported**

以上数据表明，DMIT 在主要地区的多媒体解锁能力上保持了中上水准，其中 Netflix 仅支持 Originals 节目，主流平台依旧稳定解锁。

---

## 国内三网回程路由测试

以下为国内三大运营商的回程测试结果（抽取部分路由）：

### 上海电信回程


traceroute to 202.96.209.133
1   193.41.248.72   美国 洛杉矶
2   193.41.248.130  美国 洛杉矶
3   59.43.189.37    中国 上海市 电信
4   59.43.39.117    中国 上海市 电信
...


- 平均延迟：**136 ms**

### 上海联通回程


traceroute to 210.22.97.1
1   193.41.248.72   美国 洛杉矶
2   193.41.248.130  美国 洛杉矶
3   59.43.189.33    中国 上海市 电信
...


- 平均延迟：**131 ms**

### 上海移动回程


traceroute to 211.136.112.200
1   193.41.248.72   美国 洛杉矶
2   193.41.248.130  美国 洛杉矶
3   59.43.181.145   中国 上海市 电信
...


- 平均延迟：**163 ms**

通过路由测试可以看出，DMIT 自家线路具备良好的三网覆盖和低延迟表现，特别在三网回程 CN2 GIA 路由优化方面表现出色。

---

## 国内测速概览

最后，本次测试还进行全国各地区的下载和上传多线程测速（部分结果如下）：

- **电信 | 江苏南京**：上传 **129 Mbps**，下载 **163 Mbps**，Ping **128 ms**
- **联通 | 河南郑州**：上传 **100 Mbps**，下载 **26 Mbps**，Ping **173 ms**
- **移动 | 浙江杭州**：上传 **65 Mbps**，下载 **123 Mbps**，Ping **131 ms**

---

## 总结

通过实际测试可以看出，DMIT 的 LAX PRO 产品无论是硬件支持、网络跑分还是全球测速方面都表现优异。它特别适合需要稳定上行带宽和低延迟的用户，对需要解锁国外流媒体内容的用户也有较好的支持能力。

更多 DMIT 最新优惠信息，请点击：[【推荐收藏】2025年 DMIT 最新优惠活动整理汇总 - 每日更新可用优惠套餐](https://bit.ly/dmit_coupon)