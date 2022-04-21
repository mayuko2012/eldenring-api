---
id: sorceries
title: Sorceries 请求路由
sidebar_label: Sorceries
slug: /sorceries
---

## 简介

This route fetches a list of all sorceries that can be obtained in Elden Ring, and outputs that in JSON format. The user can define his own pagination and also use search queries to find the desired output.

## 响应

| 参数名称        |      类型      |   描述 |
| ------------- | :-----------: | -----: |
| id         | `string` | Id of the sorcery |
| name         | `string` | Name of the sorcery |
| image         | `string` | Image URL of the sorcery icon |
| description         | `string` | Short description of the sorcery |
| type         | `string` | Type of Incantation |
| cost         | `number` | Cost in FP to cast this sorcery once |
| slots         | `number` | How many skill slots equipping this sorcery consumes |
| effects         | `string` | What this sorcery does |
| requires         | `{ name: string, amount: number }` | What attributes and what amount is required to cast this sorcery |

## 响应示例

```javascript
{
  success: true,
  count: 2,
  data: [{
      id: "17f69548207l0hykrjxtjpw45plt0o",
      name: "Ambush Shard",
      image: "https://eldenring-api.vercel.app/images/sorceries/17f69548207l0hykrjxtjpw45plt0o.png",
      description: "One of the night sorceries of Sellia, Town of Sorcery. Launches a projectile from a distance removed from the caster, so as to strike the enemy from behind. This sorcery can be cast repeatedly. The Sellian sorcerers were assassins, and it is said that they often hunted their fellows.",
      type: "Sorceries",
      cost: 16,
      slots: 1,
      effects: "Strikes from behind with projectile fired from distance",
      requires: [{
          name: "Intelligence",
          amount: 23
        },
        {
          name: "Faith",
          amount: 0
        },
        {
          name: "Arcane",
          amount: 0
        }
      ]
    },
    {
      id: "17f69526092l0hykrkfqubdcrri5ri",
      name: "Carian Phalanx",
      image: "https://eldenring-api.vercel.app/images/sorceries/17f69526092l0hykrkfqubdcrri5ri.png",
      description: "One of the sorceries of the Carian royal family.",
      type: "Sorceries",
      cost: 26,
      slots: 1,
      effects: "Forms a defensive arch of numerous magic glintblades",
      requires: [{
          name: "Intelligence",
          amount: 34
        },
        {
          name: "Faith",
          amount: 0
        },
        {
          name: "Arcane",
          amount: 0
        }
      ]
    }
  ]
}
```


## 请求路由

| 请求方法        |      URL      |   描述 |
| ------------- | :-----------: | -----: |
| `GET`         | https://eldenring-api.vercel.app/api/sorceries | This route retrieves a list of all the sorceries of **Elden Ring**. |
| `GET`         | https://eldenring-api.vercel.app/api/sorceries/:sorcery_id | This route retrieves one **Elden Ring** sorcery using its ID. |

## 请求参数

This route supports the following 请求参数:

| 参数名称        |      默认值      | 示例URL |  描述 |
| ------------- | :-----------: | -----: |  -----: |
| `limit`        | 20 | https://eldenring-api.vercel.app/api/sorceries?limit=100 | This parameter is used to set the maximum amount of items in the response |
| `page`         | 0 | https://eldenring-api.vercel.app/api/sorceries?limit=20&page=3 | This parameter is used no navigate between pages of results |
| `name`         | none | https://eldenring-api.vercel.app/api/sorceries?name=Carian%20Phalanx  | This parameter is used to search for fields by their names |
