---
id: armors
title: Armors 请求路由
sidebar_label: Armors
slug: /armors
---

## 简介

This route fetches a list of all armor pieces that can be encountered in Elden Ring, and outputs that in JSON format. The user can define his own pagination and also use search queries to find the desired output. 

## 响应

| 参数名称        |      类型      |   描述 |
| ------------- | :-----------: | -----: |
| id         | `string` | Id of the armor piece |
| name         | `string` | Name of the armor piece |
| image         | `string` | Image URL of the armor piece |
| description         | `string` | Short description of the armor piece |
| category         | `string` | Category of the armor piece. Example: `Leg Piece`, `Helmet`, etc. |
| weight         | `number` | How much this armor piece weights in your invetory |
| dmgNegation         | `{name: string, amount: number}` | How much damage this armor piece negates. Example: `{ "name": "Strike", amount: 6 }`|
| resistance         | `{name: string, amount: number}` | How much resistance wearing this armor piece provides. Example: `{ "name": "Poise", amount: 10 }`|

## 响应示例

```javascript
{
  success: true,
  count: 2,
  data: [{
      id: "17f696e0685l0i0nblzy58h0qvewk",
      name: "All-knowing Greaves",
      image: "https://eldenring-api.vercel.app/images/armors/17f696e0685l0i0nblzy58h0qvewk.png",
      description: "Greaves set with countless eyes and ears. Worn by Gideon Ofnir, the All-Knowing. Knowledge begins with the recognition of one's ignorance. The realization that the search for knowledge is unending. But when Gideon glimpsed into the will of Queen Marika, he shuddered in fear. At the end that should not be.",
      category: "Leg Armor",
      dmgNegation: [{
          name: "Phy",
          amount: 7
        },
        {
          name: "Strike",
          amount: 6
        },
        {
          name: "Slash",
          amount: 7
        },
        {
          name: "Pierce",
          amount: 6
        },
        {
          name: "Magic",
          amount: 7
        },
        {
          name: "Fire",
          amount: 5
        },
        {
          name: "Ligt",
          amount: 5
        },
        {
          name: "Holy",
          amount: 5
        }
      ],
      resistance: [{
          name: "Immunity",
          amount: 17
        },
        {
          name: "Robustness",
          amount: 29
        },
        {
          name: "Focus",
          amount: 13
        },
        {
          name: "Vitality",
          amount: 13
        },
        {
          name: "Poise",
          amount: 10
        }
      ],
      weight : 6.6
    },
    {
      id: "17f69515b49l0i0nbno079cqzlskebf",
      name: "All-knowing Armor",
      image: "https://eldenring-api.vercel.app/images/armors/17f69515b49l0i0nbno079cqzlskebf.png",
      description: "Armor set with countless eyes and ears. Worn by Gideon Ofnir, the All-Knowing. Knowledge begins with the recognition of one's ignorance. The realization that the search for knowledge is unending. But when Gideon glimpsed into the will of Queen Marika, he shuddered in fear. At the end that should not be.",
      category: "Chest Armor",
      dmgNegation: [{
          name: "Phy",
          amount: 12
        },
        {
          name: "Strike",
          amount: 11
        },
        {
          name: "Slash",
          amount: 13
        },
        {
          name: "Pierce",
          amount: 11
        },
        {
          name: "Magic",
          amount: 12
        },
        {
          name: "Fire",
          amount: 9
        },
        {
          name: "Ligt",
          amount: 10
        },
        {
          name: "Holy",
          amount: 8
        }
      ],
      resistance: [{
          name: "Immunity",
          amount: 28
        },
        {
          name: "Robustness",
          amount: 46
        },
        {
          name: "Focus",
          amount: 21
        },
        {
          name: "Vitality",
          amount: 21
        },
        {
          name: "Poise",
          amount: 16
        }
      ],
      weight : 10.6
    }
  ]
}
```


## 请求路由

| 请求方法        |      URL      |   描述 |
| ------------- | :-----------: | -----: |
| `GET`         | https://eldenring-api.vercel.app/api/armors | This route retrieves a list of all the armor pieces of **Elden Ring**. |
| `GET`         | https://eldenring-api.vercel.app/api/armors/:ammo_id | This route retrieves one **Elden Ring** armor piece using its ID. |

## 请求参数

This route supports the following 请求参数:

| 参数名称        |      默认值      | 示例URL |  描述 |
| ------------- | :-----------: | -----: |  -----: |
| `limit`        | 20 | https://eldenring-api.vercel.app/api/armors?limit=100 | This parameter is used to set the maximum amount of items in the response |
| `page`         | 0 | https://eldenring-api.vercel.app/api/armors?limit=20&page=3 | This parameter is used no navigate between pages of results |
| `name`         | none | https://eldenring-api.vercel.app/api/armors?name=All-knowing%20Armor  | This parameter is used to search for fields by their names |
