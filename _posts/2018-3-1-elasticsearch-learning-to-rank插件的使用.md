---
bg: "64495434_p0.jpg"
layout: post
title:  "elasticsearch-learning-to-rank插件的使用记录"
crawlertitle: "在elasticsearch中进行排序学习"
summary: "在elasticsearch中实现排序学习"
date:   2018-3-1 12:51:33 +0800
categories: posts
tags: ['信息检索']
author: haohhxx
---


最近在做检索结果打分的项目，稍微接触了下elasticsearch learning to rank这个插件。
以下简称esltr。项目地址：https://opensourceconnections.com/blog/2017/02/14/elasticsearch-learning-to-rank/
其实官方demo已经写得很详细了，这里更多记录一下使用记录和使用体验。



特征集合
-----------
首先是特征集合的构建。
在esltr中，通过在es中查询产生各种feature。
此处采用了yaml文件描述在esltr中产生feature的Query DSL，内容如下：

```yaml
featureset:
  name: name #本组特征集合的名称
  features:
  - name: 1_english_score  #首先是一个特征的名字，可以自行定义
    params: []
    template:
      function_score:  #可以定义一个在es中的DSL查询得分作为排序学习的特征，此处定义了"english"和"英语"在全部字段中的布尔查询得分
        query:
          bool:
            should:
            - query_string: {query: english}
            - query_string: {query: 英语}

  - name: 2_content_score #定义第二个特征的名字
    params: [keywords]  #可以在这里传入检索原文
    template:
      match: {content: '{{keywords}}'}  #根据上边传入的检索原文在es的content字段中进行检索，并将检索结果作为第二个特征

  - name: 3_summary_score #同上  定义第三个特征名称 
    params: [keywords]
    template:
      match: {summary: '{{keywords}}'}  # 第三个特征与第二个一样，不同的是这个特征值是在summary字段中检索得到的

  - name: 4_pr_score
    params: []
    template:
      function_score: #得到事先已经记录在索引中的值pagerank作为第四个特征
        query:
          match_all: {}
        script_score:
          script: {source: 'doc[''pagerank''].value'}

```
import yaml

with open(feature_yaml_path, 'r', encoding='utf-8') as feature_set_file:
    feature_set = yaml.load(feature_set_file)
以上是几种简单的特征产生方法。
官方文档中还有其他构建方法，包括自定义特征计算公式、语言模型查询得分等。
详见 http://elasticsearch-learning-to-rank.readthedocs.io/en/latest/


以上yaml生成dsl后直接post提交给elasticsearch，python代码如下

```python3
import requests
import json
resp = requests.put("http://localhost:9200/_ltr")
head = {'Content-Type': 'application/json'}
full_path = "http://localhost:9200/_ltr/_featureset/%s" % feature_set_name
url = "" + full_path

resp = requests.post(url=url, data=json.dumps(feature_set), headers=head)
print("post %s" % resp.status_code)
```

构建训练数据集合
---------------




