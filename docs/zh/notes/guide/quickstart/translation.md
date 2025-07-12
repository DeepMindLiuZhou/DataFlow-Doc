---
title: 案例 1. 机器翻译
createTime: 2025/06/30 19:19:16
permalink: /zh/guide/translation/
icon: basil:lightning-alt-outline
---

# 机器翻译

快速开始机器翻译。
### 第一步.安装dataflow环境
```python
pip install open-dataflow
```
### 第二步.创建新的dataflow工作文件夹
```python
mkdir run_dataflow
cd run_dataflow
```
### 第三步.初始化Dataflow
```python
dataflow init
```
这时你会看见
```python
run_dataflow/playground
```
### 第四步.填入你的api key以及api_url
```python
export DF_API_KEY=sk xx
```
api_url填写方式如下：
```
llm_serving = APILLMServing_request(
        api_url="https://api.openai.com/v1/chat/completions",
        model_name="gpt-4o",
        max_workers=100
)
```
### 第五步.准备需要翻译的数据
```jsonl
{"raw_content": "This paper presents work whose goal is to advance the field of Machine Learning. There are many potential societal consequences of our work, none which we feel must be specifically highlighted here."}
```
例如上边这种格式的数据并将数据路径填入
```python
self.storage = FileStorage(
    first_entry_file_name="your path",
    cache_path="./cache",
    file_name_prefix="raw_content",
    cache_type="jsonl",
)
```
