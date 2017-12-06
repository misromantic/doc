##### <a href="#模板标题">模板标题</a>
##### <a href="#一、轮播广告">一、轮播广告</a>
##### <a href="#二、资讯">二、资讯</a>
1. <a href="#资讯列表">资讯列表</a>

### <a name="模板标题">模板标题</a>

- *URL*

``` js
/api/banner
```

- *参数*

``` js
{}
```

- *返回*

``` js
{
  "data": {},
  "message": "查询成功",
  "stateCode": 101
}
```

### <a name="一、轮播广告">一、轮播广告</a>

- *URL*

``` js
/api/banner
```

- *参数*

``` js
{
  type: 轮播类型  1-首页
}
```

- *返回*

``` js
{
  "data": {
    "informations": [{
      "link": "http://www.yidianchina.com/netauction/auction/15266468.html?utm_source=12ZWP26",
      "picture": "http://***/assets/upload/image/b34faeb07cd6b80758baf5b85c5b303b.jpg",
      "pictureId": 15761515
    }, {
      "link": "http://www.yidianchina.com/netauction/auction/15152626.html?utm_source=12XYYJD",
      "picture": "http://***/assets/upload/image/c6d7f207bb639508f864314c3cb3de29.jpg",
      "pictureId": 15536825
    }, {
      "link": "http://***/#/news/detail/9308911?utm_source=12ZS",
      "picture": "http://picture1.yidianchina.com/assets/upload/image/61a04238272c15316c86dcc23d87797a.jpg",
      "pictureId": 15216380
    }]
  },
  "stateCode": 101
}
```

### <a name="二、资讯">二、资讯</a>
1. <a name="资讯列表">资讯列表</a>

- *URL*

``` js
/api/article/search
```

- *参数*

``` js
{
  columnId: 查询类型(0:全部,1:帖子,2:专家经验)
  userId: 查询某人资讯
  trend: 查询某人
  sortKey: 排序类型
  sortValue: 排序参数
  keyword: 关键字
  pageNum: 页码
  pageSize: 显示条目
}
```

- *返回*

``` js
{
  "data": {
    result: [{
      "id": 56542,
      "userId": 44219,
      "userType": 1,
      "type": 2,
      "title": "原来针灸减肥真的不光是说说而已!",
      "picture": [{
        "id": 123,
        "pictureUrl": "http://***"
      }, {
        "id": 456,
        "pictureUrl": "http://***"
      }],
      "publishName": "江同学",
      "portrait": "http://***",
      "publishTime": 1510927200000,
      "publishTimeValue": "刚刚",
      "label": [{
        "id": 782834,
        "name": "针灸养生"
      }, {
        "id": 527283,
        "name": "养生膳食"
      }],
      "visitCount": 10,
      "commentCount": 10,
      "praiseCount": 10,
      "hasPraised": true,
      "hasFollow": false
    }],
    totalNum: 123
    totalPage: 7
  },
  "message": "查询成功",
  "stateCode": 101
}
```
