---
id: locations
title: Locations 请求路由
sidebar_label: Locations
slug: /locations
---

## 简介

This route fetches a list of all locations that can be visited in Elden Ring, and outputs that in JSON format. The user can define his own pagination and also use search queries to find the desired output.

## 响应

| 参数名称        |      类型      |   描述 |
| ------------- | :-----------: | -----: |
| id         | `string` | Id of the location |
| name         | `string` | Name of the location |
| image         | `string` | Image URL of the location screenshot |
| description         | `string` | Short description of the location |

## 响应示例

```javascript
{
  success: true,
  count: 2,
  data: [{
      id: "17f69c5a795l0i2m72bjeqbh713r3o",
      name: "Bridge Of Sacrifice",
      image: "https://eldenring-api.vercel.app/images/locations/17f69c5a795l0i2m72bjeqbh713r3o.png",
      description: "A busy bridge swarming with iron-clad foes. Be prepared to engage in an array of melee, ranged and artillery attacks or attempt to push past them"
    },
    {
      id: "17f69869a3bl0i2m72p0sbjub568ch",
      name: "Church Of Elleh",
      image: "https://eldenring-api.vercel.app/images/locations/17f69869a3bl0i2m72p0sbjub568ch.png",
      description: "Church of Elleh is a ruined building that hides a Site of Grace. The rooftop has caved in and offers no protection from the elements, and weeds are overtaking the walls, but this doesn't stop merchants from seeking what little shelter is on offer"
    }
  ]
}
```


## 请求路由

| 请求方法        |      URL      |   描述 |
| ------------- | :-----------: | -----: |
| `GET`         | https://eldenring-api.vercel.app/api/locations | This route retrieves a list of all the creatures of **Elden Ring**. |
| `GET`         | https://eldenring-api.vercel.app/api/locations/:location_id | This route retrieves one **Elden Ring** creature using its ID. |

## 请求参数

This route supports the following 请求参数:

| 参数名称        |      默认值      | 示例URL |  描述 |
| ------------- | :-----------: | -----: |  -----: |
| `limit`        | 20 | https://eldenring-api.vercel.app/api/locations?limit=100 | This parameter is used to set the maximum amount of items in the response |
| `page`         | 0 | https://eldenring-api.vercel.app/api/locations?limit=20&page=3 | This parameter is used no navigate between pages of results |
| `name`         | none | https://eldenring-api.vercel.app/api/locations?name=Church%20Of%20Elleh  | This parameter is used to search for fields by their names |
