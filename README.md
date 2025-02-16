# 背景

对于每一位产品经理（PM）来说，产品需求文档是一个至关重要的基础工具。尤其对于初级产品经理而言，撰写出色的PRD至关重要。我希望创建一个PRD生成助手，主要有以下几点目的：

- 节省时间：在一个项目中，许多模块需要重新构建，其中很多是重复的结构化文本。
- 头脑风暴：在项目初期，可以帮助我寻找思路和灵感，特别是在不熟悉的领域。
- 资料获取：能够快速获取参考材料和总结好的信息。
- 风格统一：确保每次输出的PRD风格一致。

# 功能和实现方法

## 功能支持

* 可以基于一个产品想法或者产品名称一键生成结构化产品需求文档
* 支持丰富的指令化调整功能，每个模块都可以精确干预
* 可以联网获取信息
* 自动将内容生成飞书云文档
* 支持表格和流程图等富文本格式
* 需求文档结构可自由定制

## 实现方法

* 首选选择一个Agent平台，我这边采用的低代码开发平台：DIfy （完全是开源免费的，也提供云服务）。https://github.com/langgenius/dify
* 基础模型选用gpt4omini，也可以选择其他模型，请确保有足够长的token输出长度，模型参数设置如下：
  <img width="377" alt="image" src="https://github.com/user-attachments/assets/f12fc62a-28af-403b-ae9f-6f669dac6ad8" />

### 调用工具

* #### feishu_document

Dify自带的一个工具，可以很很方便的创建飞书文档，支持创建空文档和带内容的文档，支持 markdown 语法创建。注意：需要先在飞书创建一个机器人，然后开启机器人能力（https://open.feishu.cn/document/faq/trouble-shooting/how-to-enable-bot-ability)。后续生成的文档的所有权都是这个机器人。不用飞书的这条可以忽略。

* #### bing_web_search

Agent平台基本都会带的工具，主要用于联网查询信息，需要获取微软授权，授权方式请参考（https://www.microsoft.com/en-us/bing/apis/bing-web-search-api）

* #### current_time

dify自带，用于自动获取当前时间，用于自动生成文档创建日期。

## Prompt 设计

https://github.com/yy-hh/AutoPRD/blob/main/prompt

ps:我这边模版采用的是Markdown语法，支持图片、表格和流程图，其中流程图Mermaid语法，飞书文档都支持。

## 产品界面和效果

![image](https://github.com/user-attachments/assets/c0614cfd-c883-468b-9e58-9a63f53d8151)

# 线上体验地址：

[DEMO](https://dify-srv02.weicha88.com/chat/Nxdx7IXtsrcNVspv)

# 生成示例：

[AI情感陪伴产品需求文档V1.0](https://github.com/yy-hh/AutoPRD/blob/main/AI%E9%99%AA%E4%BC%B4%E4%BA%A7%E5%93%81%E9%9C%80%E6%B1%82%E6%96%87%E6%A1%A3V1.0.pdf)

# 基于deepseek r1 版本（效果好很多，DS 牛逼）

[AI情感陪伴产品需求文档V1.0](https://github.com/yy-hh/AutoPRD/blob/main/prd_by_deepseek.pdf)

# 微信交流：

<img src=https://github.com/user-attachments/assets/27415aaf-2e0a-42f9-9307-7336e434b8c5 width="400"/>


