# DMIT 香港 HKG EBv2 VPS 测评：三网回程 CMI，特价首发年付套餐

DMIT 近期重磅推出了全新的 HKG EBv2 VPS 产品，现有限量促销特价进行中！该款 VPS 支持三网回程 CMI，并提供优质线路，去程直连。以仅 $179.9/年的价格，可获得 1 核 CPU、1GB 内存、20GB SSD 存储、450GB 月流量及 500Mbps 带宽配置。

👉 [【推荐收藏】2025年 DMIT 最新优惠活动整理汇总 - 每日更新可用优惠套餐](https://bit.ly/dmit_coupon)

---

## DMIT HKG EBv2 产品亮点

- **三网回程 CMI**：电信回程使用 AS4809 CN2 GIA，联通和移动回程同样走高质量的 AS58453 CMI 路由。
- **去程直连**：电信通过 CTG GIA，联通经 CTG（跨境段为 AS4837，在香港切换至 AS23764），移动则通过优质的 CMI 路由。
- **无优惠码限制**：当下的首发促销特价不需要额外输入优惠码，直接下单即可享受。

---

## HKG EBv2 常规套餐及优惠码

为了满足不同用户需求，DMIT 的 HKG EB 系列提供多样化套餐选择，以下是优惠细则：

1. **新用户优惠**  
   年付套餐（TINY 及以上）可享 **85 折优惠**，需使用以下优惠码：
   
   HKG-EB-V2-ANNUALLY-15OFF-RECUR
   

2. **升级优惠**  
   老用户若从 Lite 升级至 EB 套餐，或从 EB 系列切换到 v2，可享 **15% 长期折扣**。需提交工单，并使用以下优惠码：
   
   HKG-EB-UPGRADE-TO-V2-15OFF-RECUR
   

3. **免费升级**  
   2024 年 8 月 1 日前购买的 EBv2 订单可免费升级至全新版本，配置保持不变。

---

## 网络性能及测评

### 基础配置

- **CPU**：AMD EPYC 7402P 24 核处理器，1 核 @ 2.8GHz  
- **内存**：1GB  
- **存储**：20GB SSD  
- **带宽**：500Mbps  
- **月流量**：450GB  

测试环境：Debian GNU/Linux 12 (64-bit)，BBR 拥塞控制，KVM 架构。

### 网络测速结果

#### 节点测速
| 测试节点           | 上传速度     | 下载速度     | 延迟    |
|--------------------|--------------|--------------|---------|
| 北京电信            | 1041.78 Mbps | 905.20 Mbps  | 0.28 ms |
| 新加坡 Leaseweb     | 632.33 Mbps  | 819.71 Mbps  | 36.56 ms |
| 东京                | 1001.12 Mbps | 975.49 Mbps  | 42.30 ms |
| 重庆                | 10.42 Mbps   | 0.46 Mbps    | 84.06 ms |

#### I/O 测试
平均值达到 **1.1GB/s**，读写性能表现出色，适合对稳定性有较高要求的用户。

---

## 路由及延迟表现分析

DMIT 的 HKG EBv2 系列在路由优化方面下了很大功夫，以下是常见线路的回程表现：

- **电信（CN2 GIA）**  
  路由稳定，低延迟，适合需要快速访问的远程操作或内地用户群体。
- **联通和移动（CMI）**  
  性能优越，特别是在多网回程一致性的场景下，展现出可靠的体验。

详细的回程路由报告显示，各地通过 DMIT 访问内地的延迟表现均在合理范围内。

---

## 总结

DMIT 的 HKG EBv2 VPS 是一款性价比极高的产品，适合对网络稳定性和三网优化有较高要求的用户。从配置到网络架构再到测评数据，其表现都非常出色，尤其适合作为延迟敏感性的业务使用。

如需了解更多优惠活动详情或直接购买此套餐，请参考上述优惠码信息。