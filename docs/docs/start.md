---
id: start
title: 艾尔登法环 API
sidebar_label: 开始
slug: /
---

![Elden Ring Hero](../static/img/eldenring-hero.jpg)

艾尔登法环 API 提供了 FromSoftware 在 2022 年发行的迄今为止最伟大游戏**艾尔登法环**的一些内容说明，通过此文档您可以快速了解如何使用此 API。

## THANKS TO

This repositorie is forked [eldenring-api](https://github.com/deliton/eldenring-api).  I can't thank [Deliton](https://github.com/deliton) enough who did all the hard work and motivated me to make it chinese possible.

## 中文支持

艾尔登法环 API 的数据是基于 [Deliton](https://github.com/deliton) 整理的数据所作出的中文版本。中文翻译均使用  v1.3.2 版本 **Elden Ring **中所定义的中文名称，因个人能力有限，目前仍有一些英文字段未能准确翻译。如果您有更好的意见，欢迎在我们的[仓库](https://github.com/mayuko2012/eldenring-api)中留下您的意见，更期待您的 Pr。:)

## 示例请求 (REST)

- 请求方法: **GET**
- 请求 URL: https://eldenring-api.vercel.app/api/items?limit=2

- 请求结果：

```javascript
{
  success: true,
  count: 2,
  data: [{
      id: "17f69e47912l0i1z0lip3kamll88h",
      name: "Blue Cipher Ring",
      image: "https://eldenring-api.vercel.app/images/items/17f69e47912l0i1z0lip3kamll88h.png",
      description: "Item for online play. Puts the wearer in ready state to answer should someone in another world call for rescue. You will be summoned to their world as a hunter. When summoned to rescue another player, your objective will be to defeat the invader.",
      scaling: "Reusable",
      effect: "Enables the wearer to answer calls for rescue"
    },
    {
      id: "17f69cb5ad0l0i1z0lpxlgghg1a5nd",
      name: "White Cipher Ring",
      image: "https://eldenring-api.vercel.app/images/items/17f69cb5ad0l0i1z0lpxlgghg1a5nd.png",
      description: "Item for online play. Allows you to automatically request for a hunter from another world to come to your rescue when your world is invaded. (You may be unable to summon rescuers under certain circumstances). A lost mystic code, enchanted to take the form of a ring. One of the fetishes said to have been bestowed by the Two Fingers.",
      scaling: "Reusable",
      effect: "When invaded, request the aid of a hunter."
    }
  ]
}
```

## GraphQL 支持

GraphQL 是 Facebook 在 2015 年创建的一种开源数据查询和操作语言。与传统的 REST API 相比，它提供了一种更高效和可扩展的方式来访问和更新数据。

GraphQL 允许客户端从服务器获取他们指定需要的数据，从而减少所需的请求数量和带宽。 服务器还可以将多个查询批处理到一个请求中，从而提高性能。 您可以通过访问 https://eldenring-api.vercel.app/api/graphql 开始使用数据。

## 示例请求 (GRAPHQL)

让我们检索一个名为「Giant Lobster」的怪物，希望这个 API 返回 `name`、`location` 和 `image`字段。 因此，您只需要发出一个POST请求并带上如下的GraphQL ：

```json
query {
	creature(name: "Giant Lobster") {
    name,
    location,
    image
  }
}
```

GraphQL API 将会返回以下数据：

- RESULT

```javascript
{
  "data": {
    "creature": [
      {
        "name": "Giant Lobster",
        "location": "Liurnia of the Lakes",
        "image": "https://eldenring-api.vercel.app/images/creatures/17f69d7f00al0i6ytxittgv1hoa7vg.png"
      }
    ]
  }
}
```
