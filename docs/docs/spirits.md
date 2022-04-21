---
id: spirits
title: Spirits 请求路由
sidebar_label: Spirits
slug: /spirits
---

## 简介

This route fetches a list of all spirits that can be obtained and summoned in Elden Ring, and outputs that in JSON format. The user can define his own pagination and also use search queries to find the desired output.

## 响应

| 参数名称        |      类型      |   描述 |
| ------------- | :-----------: | -----: |
| id         | `string` | Id of the spirit |
| name         | `string` | Name of the spirit |
| image         | `string` | Image URL of the spirit icon |
| description         | `string` | Short description of the spirit |
| fpCost         | `number` | Cost in FP to summon this spirit once |
| hpCost         | `number` | Cost in HP to summon this spirit once |
| effects        | `string` | What happens when we summon this spirit |

## 响应示例

```javascript
{
  success: true,
  count: 2,
  data: [{
      id: "17f69ac4bd0l0i2rc618tsrggfp3kh",
      name: "Banished Knight Oleg",
      image: "https://eldenring-api.vercel.app/images/spirits/17f69ac4bd0l0i2rc618tsrggfp3kh.png",
      description: "Ashen remains in which spirits yet dwell. Use to summon the spirit of Oleg, the Banished Knight.",
      fpCost: "100",
      hpCost: "0",
      effect: "Summons Banished Knight Oleg spirit"
    },
    {
      id: "17f69beb243l0i2rcptdnjy0wl2nxj",
      name: "Demi-human Ashes",
      image: "https://eldenring-api.vercel.app/images/spirits/17f69beb243l0i2rcptdnjy0wl2nxj.png",
      description: "Ashen remains in which spirits yet dwell. Use to summon the spirits of five demi-humans.",
      fpCost: "69",
      hpCost: "0",
      effect: "Summons five demi-human spirits"
    }
  ]
}
```


## 请求路由

| 请求方法        |      URL      |   描述 |
| ------------- | :-----------: | -----: |
| `GET`         | https://eldenring-api.vercel.app/api/spirits | This route retrieves a list of all the spirits of **Elden Ring**. |
| `GET`         | https://eldenring-api.vercel.app/api/spirits/:spirit_id | This route retrieves one **Elden Ring** spirit using its ID. |

## 请求参数

This route supports the following 请求参数:

| 参数名称        |      默认值      | 示例URL |  描述 |
| ------------- | :-----------: | -----: |  -----: |
| `limit`        | 20 | https://eldenring-api.vercel.app/api/spirits?limit=100 | This parameter is used to set the maximum amount of items in the response |
| `page`         | 0 | https://eldenring-api.vercel.app/api/spirits?limit=20&page=3 | This parameter is used no navigate between pages of results |
| `name`         | none | https://eldenring-api.vercel.app/api/spirits?name=Demi-human%20Ashes  | This parameter is used to search for fields by their names |
