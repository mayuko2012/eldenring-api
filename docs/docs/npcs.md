---
id: npcs
title: Npcs 请求路由
sidebar_label: NPCs
slug: /npcs
---

## 简介

This route fetches a list of all NPCs that can be found in Elden Ring, and outputs that in JSON format. The user can define his own pagination and also use search queries to find the desired output.

## 响应

| 参数名称        |      类型      |   描述 |
| ------------- | :-----------: | -----: |
| id         | `string` | Id of the NPC |
| name         | `string` | Name of the NPC |
| image         | `string` | Image URL of the NPC |
| description         | `string` | Short description of the NPC |
| location         | `string` | Where the NPC can be found |
| quote         | `string` | Iconic quote from that NPC |

## 响应示例

```javascript
{
  success: true,
  count: 2,
  data: [{
      id: "17f69b266a8l0i2okbqoh1wxlp59l",
      name: "Thops",
      image: "https://eldenring-api.vercel.app/images/npcs/17f69b266a8l0i2okbqoh1wxlp59l.png",
      quote: "For a small donation, I'd be happy to share my knowledge.",
      location: "Church of Irith in Liurnia of the Lakes",
      role: "Sorcery Student"
    },
    {
      id: "17f698fa9a6l0i2oki2yjnuz5pqjrh",
      name: "Enia",
      image: "https://eldenring-api.vercel.app/images/npcs/17f698fa9a6l0i2oki2yjnuz5pqjrh.png",
      quote: "The Fingers guide us all. And you Tarnished, you are here to take, are you not?",
      location: "Roundtable Hold",
      role: "Finger Reader"
    }
  ]
}
```

## 请求路由

| 请求方法        |      URL      |   描述 |
| ------------- | :-----------: | -----: |
| `GET`         | <https://eldenring-api.vercel.app/api/npcs> | This route retrieves a list of all the NPCs of **Elden Ring**. |
| `GET`         | <https://eldenring-api.vercel.app/api/npcs/:npc_id> | This route retrieves one **Elden Ring** NPC using its ID. |

## 请求参数

This route supports the following 请求参数:

| 参数名称        |      默认值      | 示例URL |  描述 |
| ------------- | :-----------: | -----: |  -----: |
| `limit`        | 20 | <https://eldenring-api.vercel.app/api/npcs?limit=100> | This parameter is used to set the maximum amount of items in the response |
| `page`         | 0 | <https://eldenring-api.vercel.app/api/npcs?limit=20&page=3> | This parameter is used no navigate between pages of results |
| `name`         | none | <https://eldenring-api.vercel.app/api/npcs?name=Enia>  | This parameter is used to search for fields by their names |
