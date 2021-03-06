# CMS

使用strapi这套系统
Nodejs: https://strapi.io/

Api docs: `https://strapi.io/documentation/3.0.0-beta.x/content-api/parameters.html#filters`

直接将项目api文件夹下的文件复制到新的项目下即可使用

## 注意事项

### 关于多语言

默认每一个语言都需要配置，对应语言 lang值如下。lang值在哪里填写，见cms平台

字段lang的值，':'后面

```text
 "languagesDic2": {
    "en-US": "English",
    "zh-CN": "中文",
    "ja": "日本語",
    "ko": "한국어",
    "fr": "Français",
    "de": "Deutsch",
    "it": "Italiano",
    "ru": "Pусский",
    "es": "Español",
    "vi": "Tiếng Việt",
    "tr": "Türkçe",
    "pt-BR": "Portuguese",
    "arabic": "عربي"
  }
```

### 2.link url之类的网页链接

示例：
https://www.baidu.com 这种, 不能缺少https://

### 3.Open字段，设置为on，才会显示数据


# 以下是涉及到aelf官网的接口

## 1.首页数据 （HotNews）

给开发的接口示例：

`http://localhost:1337/hot-news?_limit=3&_sort=id%3ADESC&lang=en&open=true`

| 字段 | 字段类型 |
| --- | --- |
| img | 媒体文件  |
| link | 文本 |
| title | 文本 |
| time | 日期 |
| lang | 文本，用来区分中英文版本 |
| open | 布尔类型 |

## 2.主网启动数据

### 2.1轮播图 （Swipers）

`http://localhost:1337/swipers?_limit=3&open=true&type=main&open=true&lang=zh&_sort=id%3ADESC`

- 目前只有rightImg生效,图片高度需要大于 600，图片内容上下居中

- type 填 main

| 字段 | 字段类型 |
| --- | --- |
| leftImg | 媒体文件 |
| rightImg | 媒体文件 |
| open | 布尔类型 |
| title | 文本 |
| desc | 文本 |
| button | 文本 |
| lang | 文本，用来区分中英文版本 |
| type | 在哪个页面展示（main/community） |

### 2.2主网启动委员会成员(ProductionNodes)

`http://localhost:1337/production-nodes?_limit=30&isStart=true&open=true&lang=zh&_sort=weight%3ADESC`

- 图片长款比为 1：1

- isStart: On

| 字段 | 字段类型 |
| --- | --- |
| open | 布尔类型（是否展示） |
| isStart | 布尔类型(是否是启动节点) |
| lang | 文本 |
| title | 文本 |
| desc | 文本(较长文字) |
| img | 媒体文件（单一） |
| website | 文本 |
| weight | 文本 |

## 3.社区治理

### 3.1 轮播图（Swipers）

数据格式同2.1

`http://localhost:1337/swipers?_limit=3&type=community&open=true&lang=zh&_sort=id%3ADESC`

- 目前只有rightImg生效,图片高度需要大于 600，图片内容上下居中

- type 填 community

### 3.2 生产节点(ProductionNodes)

数据格式同2.2

`http://localhost:1337/production-nodes?_limit=30&isStart=true&open=true&lang=zh&_sort=weight%3ADESC`

- isStart: OFF

## 4.开发案例(DevCases)

`http://localhost:1337/dev-cases?_limit=20&_sort=id%3ADESC&lang=zh&open=true`

- 图片是 400 * 200

| 字段 | 字段类型 |
| --- | --- |
| title | 文本 |
| link | 文本 |
| desc | 文本 |
| lang | 文本(较长文字) |
| img | 媒体文件（单一） |
| open | 布尔类型（是否展示） |

## 5.各种文档链接

`http://localhost:1337/papers?_limit=20&open=true&type=economic`

主要放白皮书和经济系统白皮书。
如果其它语言没有，会使用 English的版本来填充

type的值：

- 填 whitepaper是白皮书，
- 填economic 是经济系统白皮书

| 字段 | 字段类型 |
| --- | --- |
| open | 布尔类型 |
| name | 文本 |
| desc | 文本(较长的文本) |
| url | 文本 |
| type | 文本(economic / whitepaper) |
| lang | 文本 |
