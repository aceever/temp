# Elasticsearch

## 简介

> Elasticsearch是一个高度可扩展的开源全文搜索和分析引擎。它允许您快速、实时地存储、搜索和分析大量数据。它通常被用作为具有复杂搜索功能和要求的应用程序提供支持的底层引擎/技术。

Elasticsearch可以做什么？

1. 搜索
2. 收集日志或交易数据，并希望分析和挖掘这些数据以查找趋势、统计数据、摘要或异常情况。在这种情况下，可以使用Logstash (Elasticsearch/Logstash/Kibana堆栈的一部分) 来收集、聚合和解析数据，然后让Logstash将这些数据馈送到Elasticsearch中。一旦数据进入Elasticsearch，就可以运行搜索和聚合来挖掘信息。
3. 反向搜索 (Percolator) 

​		价格警报平台，允许用户指定一个价格，商品价格低于警戒价格的时候向用户发送通知

4. 使用Kibana (Elasticsearch/Logstash/Kibana堆栈的一部分) 构建自定义仪表板，以可视化对您重要的数据方面。此外，您可以使用Elasticsearch聚合功能对数据执行复杂的商业智能查询。

参考[Elastic Docs ](https://www.elastic.co/guide/index.html)

### 基本概念

- Near Realtime

  > 近乎实时

- Cluster

  > 一个或者多个节点组成集群，提供跨所有节点的联合索引和搜索功能

- Node

  > 组成集群的一台单独服务器，默认的节点名称是UUID生成的，可以修改。

- Index

  > 索引是具有某种相似特征的文档的集合。例如，您可以拥有客户数据的索引、产品目录的另一个索引以及订单数据的另一个索引。索引由名称标识 (必须全部为小写)，该名称用于在执行索引、搜索、更新、并删除对其中文档的操作。
  >
  > 在单个集群中，您可以根据需要定义任意数量的索引。

- <del>Type</del>

  > **6.0版本之后删除**
  >
  > 逻辑分片，在同一个索引中存储不同类型的文档

- Document

  >存储可被索引的信息的最基本单元

- Shards & Replicas

  > 为了解决单个索引占用容量过大的问题，Elasticsearch提供了将索引细分为多个称为分片的片段的能力。
  >
  > 创建索引时，可以指定分片的数量，每一个分片都是功能齐全且独立的“索引”，可以托管在集群的任何节点上。
  >
  > 重要作用：
  >
  > 1. 数据水平拆分
  > 2. 它允许跨分片 (可能在多个节点上) 分配和并行化操作，从而提高性能/吞吐量
  >
  > Replicas之所以重要，主要有两个原因：
  >
  > 1. 在分片/节点失败的情况下提供高可用性。出于这个原因，重要的是要注意，副本分片永远不会与从中复制它的原始/主分片分配在同一节点上。
  > 2. 它允许您扩展搜索量/吞吐量，因为搜索可以在所有副本上并行执行。

## 安装

### Windows

### Linux

```bash
curl -L -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.0.1.tar.gz

tar -xvf elasticsearch-6.0.1.tar.gz


cd elasticsearch-6.0.1/bin


./elasticsearch

./elasticsearch -Ecluster.name=my_cluster_name -Enode.name=my_node_name
```



### Docker

## 使用

elastic

kibana

## 问题



## 常见面试题

1. xxx
2. xxx
3. xxx