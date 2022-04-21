---
id: weapons
title: Weapons 请求路由
sidebar_label: Weapons
slug: /weapons
---

## 简介

This route fetches a list of all Weapons that can be obtained in Elden Ring, and outputs that in JSON format. The user can define his own pagination and also use search queries to find the desired output.

## 响应

| 参数名称        |      类型      |   描述 |
| ------------- | :-----------: | -----: |
| id         | `string` | Id of the Weapon |
| name         | `string` | Name of the Weapon |
| image         | `string` | Image URL of the Weapon |
| description         | `string` | Short description of the Weapon |
| category         | `string` | What category of Weapons. Example: `Axe`, `Sword`, etc. |
| weight          | `number` | How much the Weapon weights when equipped |
| attack         | `{ name: string, amount: number }` | How much damage the Weapon does when used as a weapon  |
| defence         | `{ name: string, amount: number }` | How much damage the Weapon blocks when used to defend an attack  |
| requiredAttributes         | `{ name: string, amount: number }` | What are the required attribute amount in order to properly use this Weapon. Example: `{ name: "Str", amount: 20 }`  |
| scalesWith         | `{ name: string, scaling: string }` | How much the Weapon scales and with what attributes. Example: `{ name: "Str", scaling: "B" }`  |

## 响应示例

```javascript
{
  success: true,
  count: 1,
  data: [{
    id: "17f695c42f0l0i1ohb4cao0qxackpu",
    name: "Forked Hatchet",
    image: "https://eldenring-api.vercel.app/images/weapons/17f695c42f0l0i1ohb4cao0qxackpu.png",
    description: "Peculiar hatchet wielded by imps. The gently undulating forked blade is known as an imps tongue and causes blood loss",
    attack: [{
        name: "Phy",
        amount: 101
      },
      {
        name: "Mag",
        amount: 0
      },
      {
        name: "Fire",
        amount: 0
      },
      {
        name: "Ligt",
        amount: 0
      },
      {
        name: "Holy",
        amount: 0
      },
      {
        name: "Crit",
        amount: 100
      }
    ],
    defence: [{
        name: "Phy",
        amount: 40
      },
      {
        name: "Mag",
        amount: 27
      },
      {
        name: "Fire",
        amount: 27
      },
      {
        name: "Ligt",
        amount: 27
      },
      {
        name: "Holy",
        amount: 27
      },
      {
        name: "Boost",
        amount: 27
      }
    ],
    scalesWith: [{
        name: "Str",
        scaling: "D"
      },
      {
        name: "Dex",
        scaling: "D"
      }
    ],
    requiredAttributes: [{
        name: "Str",
        amount: 9
      },
      {
        name: "Dex",
        amount: 14
      }
    ],
    category: "Axe",
    weight : 2.5
  }]
}
```

## 请求路由

| 请求方法        |      URL      |   描述 |
| ------------- | :-----------: | -----: |
| `GET`         | <https://eldenring-api.vercel.app/api/weapons> | This route retrieves a list of all the weapons of **Elden Ring**. |
| `GET`         | <https://eldenring-api.vercel.app/api/weapons/:weapon_id> | This route retrieves one **Elden Ring** weapon using its ID. |

## 请求参数

This route supports the following 请求参数:

| 参数名称        |      默认值      | 示例URL |  描述 |
| ------------- | :-----------: | -----: |  -----: |
| `limit`        | 20 | <https://eldenring-api.vercel.app/api/weapons?limit=100> | This parameter is used to set the maximum amount of items in the response |
| `page`         | 0 | <https://eldenring-api.vercel.app/api/weapons?limit=20&page=3> | This parameter is used no navigate between pages of results |
| `name`         | none | <https://eldenring-api.vercel.app/api/weapons?name=Forked%20Hatchet>  | This parameter is used to search for fields by their names |
