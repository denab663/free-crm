# DMIT 美国新线路 Eyeball VPS 测试与详细分析

来自美国的老牌高端主机商DMIT近日推出了美国地区的新线路——Eyeball系列VPS。据官方介绍，该系列回程均为CMIN2，适合三网直连需求。从首发促销来看，TINY及以上计划（不含月付选项）均可享受20%的折扣。本文将以PVM.LAX.EB.STARTER机型进行测试并解析其性能、网络、解锁情况及适用场景。

👉 [【推荐收藏】2025年 DMIT 最新优惠活动整理汇总 - 每日更新可用优惠套餐](https://bit.ly/dmit_coupon)

---

## 1. 综合性能评测

**硬件配置**  
测试机型：PVM.LAX.EB.STARTER  
配置参数：2vCore | 2GB 内存 | 40GB SSD | 每月进出流量4500GB  

本次性能测试采用了行业常见工具YABS，涵盖GB5和GB6评测。CPU为AMD第二代EPYC 7402P，基准主频为2.8GHz。该设备初期性能较为充分，但与部分高性能系列相比亮点较少。

plaintext
Processor  : AMD EPYC 7402P 24-Core Processor
CPU cores  : 2 @ 2794.684 MHz
AES-NI     : ✔ Enabled
VM-x/AMD-V : ✔ Enabled

fio Disk Speed Tests (Mixed R/W 50/50) (Partition /dev/vda3):
---------------------------------
Block Size | 4k            (IOPS) | 64k           (IOPS)
Read       | 19.18 MB/s    (4.7k) | 296.60 MB/s   (4.6k)
Write      | 19.19 MB/s    (4.7k) | 298.16 MB/s   (4.6k)
Total      | 38.38 MB/s    (9.5k) | 594.76 MB/s   (9.2k)

Block Size | 512k          (IOPS) | 1m            (IOPS)
Read       | 1.02 GB/s     (1.9k) | 1.01 GB/s      (987)
Write      | 1.07 GB/s     (2.1k) | 1.07 GB/s     (1.0k)
Total      | 2.10 GB/s     (4.1k) | 2.08 GB/s     (2.0k)

Geekbench 5:
Single Core: 894  
Multi Core: 1673  
Test URL: https://browser.geekbench.com/v5/cpu/22392603

Geekbench 6:
Single Core: 1172  
Multi Core: 2113  
Test URL: https://browser.geekbench.com/v6/cpu/5688383


---

## 2. 回程网络质量

根据官方信息，Eyeball系列支持三网去程直连，回程均走CMIN2链路。适合对低延迟有需求的用户，且Debian模板默认启用了BBR优化。

回程质量测试结果如下：

plaintext
CT > DMIT: - AS4809
CU > DMIT: - AS4134 > AS4809
CM > DMIT: - AS58807

DMIT > CT CU CM: AS58807

Test IP:
IPv4: 154.17.226.2  
IPv6: 2605:52c0:1:3:2c2a:59ff:fe05:65c2


各大运营商回程分析：

plaintext
# 电信
193.41.248.137  美国 加州 洛杉矶 DMIT.com
223.120.197.5   美国 加州 洛杉矶 移动
202.97.65.181   中国 湖北 武汉 电信

# 联通
193.41.248.137  美国 加州 洛杉矶 DMIT.com
223.120.197.5   美国 加州 洛杉矶 移动
219.158.113.197 中国 上海 联通

# 移动
193.41.248.137  美国 加州 洛杉矶 DMIT.com
223.120.161.5   中国 上海 移动
221.183.109.98  中国 广东 广州 移动


---

## 3. 网站解锁情况

DMIT使用的是祖传Cogent IP，根据评测，网站解锁表现具有地域限制，需视具体IP分配情况。

### IPv4解锁结果：

plaintext
Dazn:               Yes (Region: US)  
HotStar:            Yes (Region: US)  
Disney+:            No  
Netflix:            Originals Only  
YouTube Premium:    Yes  
Amazon Prime Video: Yes (Region: US)  
Spotify:            Yes (Region: US)


### IPv6解锁结果：

plaintext
Dazn:               Failed  
HotStar:            Yes (Region: US)  
Netflix:            Yes (Region: US)  
TVBAnywhere+:       Failed  
Spotify:            Yes (Region: US)  
Steam Currency:     Failed  
Bing Region:        US  


---

## 4. 用户购买建议

Eyeball系列定位高于CU4837线路产品，与CN2 GIA系列的性能较接近。对于联通和移动用户来说，此系列具备较高性价比，推荐考虑。电信用户则可能需结合自身实际需求选择是否购买。移动用户在亚太区域的选择较多，联通用户可用9929线路补充。

此外，有传闻称LAX WEE系列可能近期补货，不急于购买的用户可持币等待。

markdown
👉 [【推荐收藏】2025年 DMIT 最新优惠活动整理汇总 - 每日更新可用优惠套餐](https://bit.ly/dmit_coupon)