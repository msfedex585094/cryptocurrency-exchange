# DMIT HKG.T1.TINY 性能评测：月付 6.9 美元，年付 36.9 美元

DMIT 的 HKG.T1.TINY 套餐备受关注，尤其是在接入 RETN 网络后，通过广港专线，在英国等地的落地速度表现较为优秀。本次我们对其性能进行了全面评测，涵盖 YABS 性能、网络回程测试和单线程测速等多方面内容。

---

## YABS 性能测试

以下是通过 YABS（Yet Another Bench Script）脚本对基础性能的测试结果：

plaintext
# ## ## ## ## ## ## ## ## ## ## ## ## ## ## ## ## ## #
#              Yet-Another-Bench-Script              #
#                     v2023-09-06                    #
# https://github.com/masonr/yet-another-bench-script #
# ## ## ## ## ## ## ## ## ## ## ## ## ## ## ## ## ## #

Thu Sep 21 08:53:58 UTC 2023

Basic System Information:
---------------------------------
Uptime     : 0 days, 0 hours, 10 minutes
Processor  : AMD EPYC 7402P 24-Core Processor
CPU cores  : 1 @ 2794.750 MHz
AES-NI     : ✔ Enabled
VM-x/AMD-V : ✔ Enabled
RAM        : 724.4 MiB
Swap       : 0.0 KiB
Disk       : 9.7 GiB
Distro     : Debian GNU/Linux 11 (bullseye)
Kernel     : 5.10.0-16-amd64
VM Type    : KVM
IPv4/IPv6  : ✔ Online / ✔ Online

IPv6 Network Information:
---------------------------------
ISP        : DMIT Cloud Services
ASN        : AS906 DMIT Cloud Services
Host       : Dmitinc
Location   : Los Angeles, California (CA)
Country    : United States

fio 磁盘读写测试:
---------------------------------
Block Size | 4k            (IOPS) | 64k           (IOPS)
  ------   | ---            ----  | ----           ---- 
Read       | 10.64 MB/s    (2.6k) | 162.21 MB/s   (2.5k)
Write      | 10.66 MB/s    (2.6k) | 163.07 MB/s   (2.5k)
Total      | 21.30 MB/s    (5.3k) | 325.29 MB/s   (5.0k)

Block Size | 512k          (IOPS) | 1m            (IOPS)
  ------   | ---            ----  | ----           ---- 
Read       | 498.26 MB/s    (973) | 491.53 MB/s    (480)
Write      | 524.73 MB/s   (1.0k) | 524.27 MB/s    (511)
Total      | 1.02 GB/s     (1.9k) | 1.01 GB/s      (991)

iperf3 网络测速 (IPv4):
---------------------------------
伦敦 Clouvider（10G）      | 920 Mbps 上传 | 641 Mbps 下载 | 延迟 222 ms
巴黎 Scaleway（10G）      | 1.26 Gbps 上传 | 1.19 Gbps 下载 | 延迟 163 ms
洛杉矶 Clouvider（10G）  | 691 Mbps 上传 | 580 Mbps 下载 | 延迟 161 ms

iperf3 网络测速 (IPv6):
---------------------------------
伦敦 Clouvider（10G）      | 706 Mbps 上传 | 565 Mbps 下载 | 延迟 222 ms
巴黎 Scaleway（10G）      | 1.28 Gbps 上传 | 848 Mbps 下载 | 延迟 164 ms
洛杉矶 Clouvider（10G）  | 1.06 Gbps 上传 | 654 Mbps 下载 | 延迟 159 ms

测试总耗时：9 分 20 秒


---

👉 [【推荐收藏】2025年 DMIT 最新优惠活动整理汇总 - 每日更新可用优惠套餐](https://bit.ly/dmit_coupon)

---

## 三网回程路由测试

我们通过测试工具对三网（电信、联通、移动）的回程路由进行了评估，但所有节点均出现超时情况：

plaintext
测试时间: 2023/09/21
国家: 香港
城市: Hong Kong
服务商: AS906 DMIT Cloud Services

北京电信 219.141.136.12   测试超时  
北京联通 202.106.50.1     测试超时  
北京移动 221.179.155.161  测试超时  
上海电信 202.96.209.133   测试超时  
广州电信 58.60.188.222    测试超时
成都联通 119.6.6.6        测试超时


以上测试结果反映可能存在国内访问较弱的情况，适合海外落地加速和轻度使用需求。

---

## 单线程测速结果

通过 HyperSpeed 脚本（更新于 2023 年 4 月），对部分精选地区的单线程上传、下载速率进行了测评：

plaintext
测速服务器信息   ↑ 上传/Mbps ↓ 下载/Mbps ↕ 延迟/ms ϟ 抖动/ms
香港|环电宽频    ↑ 4159.8 正常 ↓ 2242.7 正常 ↕ 1.3 ϟ 0.1
澳门|澳门电讯    ↑ 4119.4 正常 ↓ 734.7 正常  ↕ 3.4 ϟ 0.1
台北|中华电信    ↑ 2749.0 正常 ↓ 964.6 正常  ↕ 23.8 ϟ 25.3
东京|乐天移动    ↑ 2264.7 正常 ↓ 117.9 正常  ↕ 45.8 ϟ 8.3
首尔|Kdatacenter ↑  302.6 正常 ↓  31.2 正常  ↕ 38.7 ϟ 30.2


本次测速主要集中于港澳台及日韩地区，对香港的表现尤为满意，延迟低至 1.3ms，适合对高带宽要求的业务。

---

## 总结

DMIT HKG.T1.TINY 套餐以高性价比和跨境网络的优异表现成为理想选择，适合海外跨境数据传输、留学党、轻度外贸或媒体访问等场景。然而，其在国内三网的表现稍显不足，更推荐用于国际流量需求场景。

详细套餐信息可参考[DMIT 官方优惠活动](https://bit.ly/dmit_coupon)，趁促销获取更划算的方案吧！