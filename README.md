### <a href="#一、轮播广告">一、轮播广告</a>
### <a href="#二、资讯">二、资讯</a>
1. <a href="#资讯列表">资讯列表</a>
2. <a href="#资讯详情">资讯详情</a>
3. <a href="#待编辑资讯实体">待编辑资讯实体</a>
4. <a href="#发布资讯">发布资讯</a>
5. <a href="#资讯标签">资讯标签</a>

### <a href="#三、评论">三、评论</a>
1. <a href="#获取评论">获取评论</a>


> 模板 being

### <a name="一、模板标题">一、模板标题</a>
1. <a name="模板标题">模板标题</a>
- *URL*

``` js
/api/
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

> 模板 end


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


2. <a name="资讯详情">资讯详情</a>
- *URL*

``` js
/api/article/{id}
```

- *参数*

``` js
{}
```

- *返回*

``` js
{
  "data": {
    "id": 90844,
    "userId": 192908,
    "publishName": "江同学",
    "portrait": "http://***",
    "userAuditType": 1,
    "type": 2,
    "title": "如何简单的明确病变的性质",
    "picture": [{
      "id": 4234,
      "url": "http://**"
    }, {
      "id": 6546,
      "url": "http://***"
    }],
    "content": "在临床上按中医的诊疗方法............",
    "createTime": 1510927200000,
    "createTimeValue": "刚刚",
    "commentCount": 12,
    "praiseCount": 100,
    "hasFollow": false,
    "whetherSelf": false // 标识是否是文章发布者
  },
  "message": "查询成功",
  "stateCode": 101
}
```

3. <a name="待编辑资讯实体">待编辑资讯实体</a>
- *URL*

``` js
/api/article/entity/{id}
```

- *参数*

``` js
{}
```

- *返回*

``` js
{
  "data": {
    "id": 0,
    "title": "标题",
    "content": "内容",
    "pictures": [{
      "id": 564,
      "url": "http://localhost:8080/assets/upload/product/0778f117551de2a7137531a80bc83ff7.png",
    }, {
      "id": 565,
      "url": "http://localhost:8080/assets/upload/product/0fc2c18780a18df4f2766a7db631aca0.png",
    }],
    "labels": [{
      "id": 499,
      "name": "膳食"
    }, {
      "id": 500,
      "name": "滋补"
    }],
    "whetherDraft": false // 是否是草稿
  },
  "message": "成功",
  "stateCode": 101
}
```

4. <a name="发布资讯">发布资讯</a>
- *URL*

``` js
/api/article/publish
```

- *参数*

``` js
{
  id: 传0代表新增
  title: 标题
  context: 正文
  pictures: [id, id, id] 图片集合
  labels: [id, id, id] 标签集合
}
```

- *返回*

``` js
{
  "data": {},
  "message": "查询成功",
  "stateCode": 101
}
```

5. <a name="资讯标签">资讯标签</a>
- *URL*

``` js
/api/label
```

- *参数*

``` js
{}
```

- *返回*

``` js

{
  "data": {
    "result": [{
      "id": 5234,
      "name": "热门",
      "labels": [{
        "id": 3,
        "name": "养生"
      }, {
        "id": 5,
        "name": "美容"
      }]
    }, {
      "id": 555,
      "name": "饮食",
      "labels": [{
        "id": 11,
        "name": "芬达"
      }, {
        "id": 22,
        "name": "雪碧"
      }]
    }]
  },
  "message": "查询成功",
  "stateCode": 101
}
```

### <a name="三、评论">三、评论</a>
1. <a name="获取评论">获取评论</a>
- *URL*

``` js
/api/comment
```

- *参数*

``` js
{
  sourceId: 资源标识
}
```

- *返回*

``` js
{
  "data": {},
  "message": "查询成功",
  "stateCode": 101
}
```
