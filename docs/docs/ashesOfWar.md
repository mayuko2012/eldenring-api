---
id: ashes
title: Ashes of War 请求路由
sidebar_label: Ashes of War
slug: /ashes
---

## 简介

This route fetches a list of all ashes of war that can be encountered in Elden Ring, and outputs that in JSON format. The user can define his own pagination and also use search queries to find the desired output.

## 响应

| 参数名称        |      类型      |   描述 |
| ------------- | :-----------: | -----: |
| id         | `string` | Id of the ash of war item |
| name         | `string` | Name of the ash of war item |
| image         | `string` | Image URL of the ash of war item |
| description         | `string` | Short description of the ash of war item |
| affinity         | `string` | Affinity of an Ash of War. |
| skill         | `string` | Skill activated when this Ash of War is equipped in a weapon |

## 响应示例

```javascript
{
  success: true,
  count: 2,
  data: [{
      id: "17f699db6b0l0hzn9xsxxwtgyfky3",
      name: "Ash Of War: Prelate's Charge",
      image: "https://eldenring-api.vercel.app/images/ashes/17f699db6b0l0hzn9xsxxwtgyfky3.png",
      description: "This Ash of War grants an armament the Flame affinity and the following skill:"
      Prelate 's Charge: Slam armament into the ground to create a surge of flames, then charge in. Hold to continue the charge."Usable on large and colossal axes and hammers.",
      affinity: "Flame",
      skill: "Prelate's Charge"
    },
    {
      id: "17f69632311l0hzna19sl4rzmmvk4",
      name: "Ash Of War: Barrage",
      image: "https://eldenring-api.vercel.app/images/ashes/17f69632311l0hzna19sl4rzmmvk4.png",
      description: "This Ash of War grants no affinity to an armament, but imparts the following skill:"
      Barrage: Archery skill using a bow held horizontally
        .Ready the bow,
      then fire off a rapid succession of
      shots faster than the eye can see
      .
      "Usable on light bows.",
      affinity: "Standard",
      skill: "Barrage"
    }
  ]
}
```

## 请求路由

| 请求方法        |      URL      |   描述 |
| ------------- | :-----------: | -----: |
| `GET`         | <https://eldenring-api.vercel.app/api/ashes> | This route retrieves a list of all the ashes of war present in **Elden Ring**. |
| `GET`         | <https://eldenring-api.vercel.app/api/ashes/:ash_of_war_id> | This route retrieves one **Elden Ring** Ash of War using its ID. |

## 请求参数

This route supports the following 请求参数:

| 参数名称        |      默认值      | 示例URL |  描述 |
| ------------- | :-----------: | -----: |  -----: |
| `limit`        | 20 | <https://eldenring-api.vercel.app/api/ashes?limit=100> | This parameter is used to set the maximum amount of items in the response |
| `page`         | 0 | <https://eldenring-api.vercel.app/api/ashes?limit=20&page=3> | This parameter is used no navigate between pages of results |
| `name`         | none | <https://eldenring-api.vercel.app/api/ashes?name=Ash%20Of%20War:%20Prelate's%20Charge>  | This parameter is used to search for fields by their names |
