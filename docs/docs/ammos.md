---
id: ammos
title: 箭类
sidebar_label: Ammos
slug: /ammos
---

## 简介

该 API 将获取 **Elden Ring** 中可能遇到的所有的箭类列表，并以 JSON 格式输出。 支持分页查询，也支持使用搜索条件来查询。

## 响应

| 参数名称        |      类型      |   描述 |
| ------------- | :-----------: | :----- |
| id         | `string` | 唯一ID |
| name         | `string` | 名称 |
| image         | `string` | 图像 |
| description         | `string` | 描述 |
| type         | `string` | 伤害类型 |
| passive         | `string` | 造成的被动效果，比如出血、中毒等 |
| attackPower         | `{name: string, amount: number}` | 在每种伤害下的分类，比如： `{ "name": "Phys", amount: 50 }` |

## 响应示例

```javascript
{
    "success": true,
    "count": 2,
    "total": 53,
    "data": [
        {
            "id": "17f69448ceel0i0a57bokoqz409yb",
            "name": "兽骨火箭",
            "name_en": "Firebone Arrow",
            "image": "https://eldenring-api.vercel.app/images/ammos/17f69448ceel0i0a57bokoqz409yb.png",
            "description": "在箭头点燃火焰的兽骨箭。\n能给予火属性伤害。\n\n能够制作的其中一项道具。",
            "type": "Pierce",
            "passive": "-",
            "attackPower": [
                {
                    "name": "Phy",
                    "amount": 10
                },
                {
                    "name": "Mag",
                    "amount": 0
                },
                {
                    "name": "Fire",
                    "amount": 90
                },
                {
                    "name": "Ligt",
                    "amount": 0
                },
                {
                    "name": "Holy",
                    "amount": 0
                },
                {
                    "name": "Crit",
                    "amount": 100
                }
            ]
        },
        {
            "id": "17f695dc715l0i0a59pf1x5fb5112r",
            "name": "兽骨出血箭（附箭羽）",
            "name_en": "Bloodbone Arrow (Fletched)",
            "image": "https://eldenring-api.vercel.app/images/ammos/17f695dc715l0i0a59pf1x5fb5112r.png",
            "description": "在箭头涂上血药膏的兽骨箭。\n具有引发异常状态出血的效果。\n\n能够制作的其中一项道具。\n附上箭羽之后，提升了飞翔距离。",
            "type": "Pierce",
            "passive": "Causes blood loss build up (55)",
            "attackPower": [
                {
                    "name": "Phy",
                    "amount": 25
                },
                {
                    "name": "Mag",
                    "amount": 0
                },
                {
                    "name": "Fire",
                    "amount": 0
                },
                {
                    "name": "Ligt",
                    "amount": 0
                },
                {
                    "name": "Holy",
                    "amount": 0
                },
                {
                    "name": "Crit",
                    "amount": 100
                }
            ]
        }
    ]
}
```


## 请求路由

| 请求方法        |      URL      |   描述 |
| ------------- | :-----------: | :----- |
| `GET`         | https://eldenring-api.vercel.app/api/ammos | 将返回 **Elden Ring** 中所有箭类的数据 |
| `GET`         | https://eldenring-api.vercel.app/api/ammos/:ammo_id | 将返回 **Elden Ring** 中指定 ID 的数据 |

## 请求参数

该 API 支持以下请求参数:

| 参数名称        |      默认值      | 示例URL |  描述 |
| ------------- | :-----------: | :----- |  :----- |
| `limit`        | 20 | https://eldenring-api.vercel.app/api/ammos?limit=100 | 每次返回 100 条数据 |
| `page`         | 0 | https://eldenring-api.vercel.app/api/ammos?limit=20&page=3 | 分页查询 |
| `name`         | none | https://eldenring-api.vercel.app/api/ammos?name=Firebone%20Arrow  | 通过 name 字段进行查询 |
