---
id: classes
title: Classes 请求路由
sidebar_label: Classes
slug: /classes
---

## 简介

This route fetches a list of the initial classes that can be selected in Elden Ring's character creation, and outputs that in JSON format. The user can define his own pagination and also use search queries to find the desired output.

## 响应

| 参数名称        |      类型      |   描述 |
| ------------- | :-----------: | -----: |
| id         | `string` | Id of the class |
| name         | `string` | Name of the class |
| image         | `string` | Image URL of the class character using the initial equipment provided |
| description         | `string` | Short description of the class |
| stats         | `{ level: string, vigor: string, mind: string, endurance: string, strength: string, dexterity: string, intelligence: string, faith: string, arcane: string}` | Initial stats of the class |

## 响应示例

```javascript
{
  success: true,
  count: 2,
  data: [{
      id: "17f69d71826l0i32gkm3ndn3kywxqj",
      name: "Hero",
      image: "https://eldenring-api.vercel.app/images/classes/17f69d71826l0i32gkm3ndn3kywxqj.png",
      description: "A stalwart Hero, at home with a battleaxe, descended from a badlands chieftain",
      stats: {
        level: "7",
        vigor: "14",
        mind: "9",
        endurance: "12",
        strength: "16",
        dexterity: "9",
        inteligence: "7",
        faith: "8",
        arcane: "11"
      }
    },
    {
      id: "17f69b2dd76l0i32gljr3f62pkzhjo",
      name: "Warrior",
      image: "https://eldenring-api.vercel.app/images/classes/17f69b2dd76l0i32gljr3f62pkzhjo.png",
      description: "A twinblade wielding warrior from a nomadic tribe. An origin of exceptional technique",
      stats: {
        level: "8",
        vigor: "11",
        mind: "12",
        endurance: "11",
        strength: "10",
        dexterity: "16",
        inteligence: "10",
        faith: "8",
        arcane: "9"
      }
    }
  ]
}
```

## 请求路由

| 请求方法        |      URL      |   描述 |
| ------------- | :-----------: | -----: |
| `GET`         | <https://eldenring-api.vercel.app/api/classes> | This route retrieves a list of all the classes in **Elden Ring**. |
| `GET`         | <https://eldenring-api.vercel.app/api/classes/:class_id> | This route retrieves one **Elden Ring** class using its ID. |

## 请求参数

This route supports the following 请求参数:

| 参数名称        |      默认值      | 示例URL |  描述 |
| ------------- | :-----------: | -----: |  -----: |
| `limit`        | 20 | <https://eldenring-api.vercel.app/api/classes?limit=100> | This parameter is used to set the maximum amount of items in the response |
| `page`         | 0 | <https://eldenring-api.vercel.app/api/classes?limit=20&page=3> | This parameter is used no navigate between pages of results |
| `name`         | none | <https://eldenring-api.vercel.app/api/classes?name=Hero>  | This parameter is used to search for fields by their names |
