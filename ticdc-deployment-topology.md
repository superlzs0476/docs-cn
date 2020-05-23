---
title: TiCDC 部署拓扑
category: how-to
---

# TiCDC 部署拓扑

## 部署需求

通过 `tidb` 用户做集群管理，部署 3 个节点的 TiCDC 集群，使用默认 `22` 端口，部署目录为 `/tidb-deploy`，数据目录为 `/tidb-data`。

## 部署规划


## 拓扑信息

|实例 | 个数 | 物理机配置 | IP |配置 |
| :-- | :-- | :-- | :-- | :-- |
| TiDB |3 | 16 VCore 32GB * 1 | 10.0.1.1 <br> 10.0.1.2 <br> 10.0.1.3 | 默认端口 <br>  全局目录配置 |
| PD | 3 | 4 VCore 8GB * 1 |10.0.1.4 <br> 10.0.1.5 <br> 10.0.1.6 | 默认端口 <br> 全局目录配置 |
| TiKV | 3 | 16 VCore 32GB 2TB (nvme ssd) * 1 | 10.0.1.7 <br> 10.0.1.8 <br> 10.0.1.9 | 默认端口 <br> 全局目录配置 |
| CDC | 3 | 8 VCore 16GB * 1 | 10.0.1.11 <br> 10.0.1.12 <br> 10.0.1.13 | 默认端口 <br> 全局目录配置 |
| Monitoring & Grafana | 1 | 4 VCore 8GB * 1 500GB (ssd) | 10.0.1.11 | 默认端口 <br> 全局目录配置 |

## 拓扑图

待添加

## 配置文件模版 topology.yaml

[简单 TiCDC 配置](/simple-mini.yaml)
[复杂 TiCDC 配置](/complex-mini.yaml)

> **注意：**
>
> - 无需手动创建 tidb 用户，TiUP cluster 组件会在部署主机上自动创建该用户。可以自定义用户，也可以和中控机的用户保持一致。