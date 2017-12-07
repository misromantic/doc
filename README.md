### <a href="#一、轮播广告">一、轮播广告</a>
### <a href="#二、资讯">二、资讯</a>
1. <a href="#资讯列表">资讯列表</a>
2. <a href="#资讯详情">资讯详情</a>
3. <a href="#待编辑资讯实体">待编辑资讯实体</a>
4. <a href="#发布资讯">发布资讯</a>
5. <a href="#资讯标签">资讯标签</a>

### <a href="#三、评论">三、评论</a>
1. <a href="#获取评论">获取评论</a>
2. <a href="#发布评论/回复">发布评论/回复</a>

### <a href="#四、专题">四、专题</a>
1. <a href="#专题列表">专题列表</a>
2. <a href="#专题详情">专题详情</a>

### <a href="#五、个人主页">五、个人主页</a>
1. <a href="#个人信息">个人信息</a>

### <a href="#六、会员中心">六、会员中心</a>
1. <a href="#个人中心">个人中心</a>
2. <a href="#修改基础信息">修改基础信息</a>
3. <a href="#点赞">点赞</a>
4. <a href="#关注">关注</a>
5. <a href="#关注列表">关注列表</a>

### <a href="#七、个人认证">七、个人认证</a>
1. <a href="#医生认证">医生认证</a>
2. <a href="#机构认证">机构认证</a>
3. <a href="#机构类型">机构类型</a>


### <a name="模板主标题">模板主标题</a>
1. <a name="模板副标题">模板副标题</a>
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



### <a name="一、轮播广告">一、轮播广告</a>

- *URL*

``` js
/api/banner
```

- *参数*

``` js
{
  type:  // 轮播类型  1-首页
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
  columnId: , // 查询类型(0:全部,1:帖子,2:专家经验)
  userId: , // 查询某人资讯
  trend: , // 查询某人
  sortKey: , // 排序类型
  sortValue: , // 排序参数
  keyword: , // 关键字
  pageNum: , // 页码
  pageSize: // 显示条目
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
  id: , // 传0代表新增
  title: , // 标题
  context: , // 正文
  pictures: [id, id, id] , // 图片集合
  labels: [id, id, id] , // 标签集合
}
```

- *返回*

``` js
{
  "message": "发布成功",
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
    }]
  },
  "message": "查询成功",
  "stateCode": 101
}
```

### <a name="三、评论">三、评论</a>
1. <a name="获取评论">获取评论</a>
- *URL*

``` js
/api/comment
```

- *参数*

``` js
{
  sourceId: // 资源标识
}
```

- *返回*

``` js
{
    "data":
    {
        "result": [
        {
            "id": 24234,
            "name": "用户A",
            "userId": 23490823,
            "portrait": "http://***",
            "createTime": 111129084098,
            "createTimeValue": "7-11",
            "content": "不错不错",
            "replys": [] // 该条评论的全部回复集合
        }],
        "totalNum": 123,
        "totalPage": 7
    },
    "message": "查询成功",
    "stateCode": 101
}
```

2. <a name="发布评论/回复">发布评论/回复</a>
- *URL*

``` js
/api/comment/add
```

- *参数*
``` js
{
  sourceId: , // 资源标识
  sourceType: , // 资源类型
  content: // 评论or回复内容
}
```

- *返回*

``` js
{
  "message": "评论成功",
  "stateCode": 101
}
```

### <a name="四、专题">四、专题</a>
1. <a name="专题列表">专题列表</a>
- *URL*

``` js
/api/topic/search
```

- *参数*

``` js
{
  sortKey: , // 排序类型
  sortType: , // 排序方式
  pageNum: , //页码
  pageSize: // 显示条目
}
```

- *返回*

``` js
{
  "data": {
    "result": [{
        "id": 24234,
        "name": "十种元气早餐",
        "pictureUrl": "http://***",
        "articleCount": 20,
        "commentCount": 199
      },],
    "totalNum": 123,
    "totalPage": 7
  },
  "message": "查询成功",
  "stateCode": 101
}
```

2. <a name="专题详情">专题详情</a>
- *URL*

``` js
/api/topic/{id}
```

- *参数*

``` js
{}
```

- *返回*

``` js
{
  "data": {
    "id": 24234,
    "name": "十种元气早餐",
    "pictureUrl": "http://***",
    "articleCount": 20,
    "commentCount": 199,
    "articles": [{

    }]
  },
  "message": "查询成功",
  "stateCode": 101
}
```

### <a name="五、个人主页">五、个人主页</a>
1. <a name="个人信息">个人信息</a>
- *URL*

``` js
/api/homepage/{id}
```

- *参数*

``` js
{}
```

- *返回*

``` js
{
    "data": {
        "portrait": "http://***",
        "hasFollow": true,
        "followCount": 10,
        "byFollowCount": 20,
        "whetherSelf": true,
        "userAuditType": true
    },
    "message": "查询成功",
    "stateCode": 101
}
```

### <a name="六、会员中心">六、会员中心</a>
1. <a name="个人中心">个人中心</a>
- *URL*

``` js
/api/user/center
```

- *参数*

``` js
{}
```

- *返回*

``` js
{
  "data": {
    "userId": 1030,
    "userAuditType":100001,
    "userAuditStatus":200101,
    "portrait": "",
    "name": "",
    "articleCount": 10,
    "followCount", 10,
    "byFollowCount": 20,
    "followArticleCount":10,
    "commentCount":10
  },
  "message": "查询成功",
  "stateCode": 101
}
```

2. <a name="修改基础信息">修改基础信息</a>
- *URL*

``` js
/api/user/update
```

- *参数*

``` js
{
  nickName: // 昵称
}
```

- *返回*

``` js
{
  "message": "操作成功",
  "stateCode": 101
}
```

3. <a name="点赞">点赞</a>
- *URL*

``` js
/api/praise
```

- *参数*

``` js
{
  sourceId: , // 被赞标识
  sourceType: // 被赞类型
}
```

- *返回*

``` js
{
  "message": "操作成功",
  "stateCode": 101
}
```

4. <a name="关注">关注</a>
- *URL*

``` js
/api/follow
```

- *参数*

``` js
{
  sourceId: , // 被关注标识
  sourceType: // 被关注类型
}
```

- *返回*

``` js
{
  "message": "操作成功",
  "stateCode": 101
}
```

5. <a name="关注列表">关注列表</a>
- *URL*

``` js
/api/follow/search
```

- *参数*

``` js
{
  userId: , // 查询某人关注列表
  trend: , // 查询某人被关注列表
  pageNum: , // 页码
  pageSize: // 显示条目
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

### <a name="七、个人认证">七、个人认证</a>
1. <a name="医生认证">医生认证</a>
- *URL*

``` js
/api/user/approve
```

- *参数*

``` js
{
    realName: , // 真实姓名
    gender: , // 性别
    professionTitle: , // 职称
    workMobile: , // 工作电话
    organization: , // 所属机构
    city: , // 城市
    profile: , // 个人介绍
    primaryFiled: , // 擅长领域
    idCardFront: { // 身份证正面
        id: , // 图片标识
        url: // 图片地址
    }
    idCardBack: { // 身份证反面
        id: ,
        url:
    },
    idCardHand: { // 手持身份证照片
        id: ,
        url:
    },
    bareheadedPhotoId: { // 免冠清晰正面照标
        id: ,
        url:
    },
    practicingCertificate: { // 医师执业证图片
        id: ,
        url:
    },
    professionCertificate: { // 医师职称证图片
        id: ,
        url:
    }
}
```

- *返回*

``` js
{
  "message": "操作成功",
  "stateCode": 101
}
```

2. <a name="机构认证">机构认证</a>
- *URL*

``` js
/api/user/approve/organization
```

- *参数*

``` js
{
    type: {
        id: , // 机构类型标识
        name: // 机构类型名称
    },
    name: , // 机构名称
    registrationNumber: , // 注册号
    address: , // 机构地图地址
    addressDetail: , // 手写详细地址
    addressPoint: { //地图坐标
        longitude, // 经度
        latitude // 纬度
    },
    workMobile: , // 工作电话
    legalPersonName: , // 法人姓名
    profile: , // 机构介绍
    primaryFiled: , // 擅长领域
    businessLicenseFront: { // 营业执照图片
        id: , //  图片标识,
        url: // 图片地址
    },
    legalPersonIdCardFront: { // 法人身份证正面图片
        id: ,
        url:
    },
    legalPersonIdCardBack: { //法人身份证反面图片
        id: ,
        url:
    }
}
```

- *返回*

``` js
{
  "message": "操作成功",
  "stateCode": 101
}
```

3. <a name="机构类型列表">机构类型列表</a>
- *URL*

``` js
/api/organization/type
```

- *参数*

``` js
{}
```

- *返回*

``` js
{
    "data":{
        "result": [{
            "id": 5234,
            "name": "按摩"
        }]
    },
    "message": "查询成功",
    "stateCode": 101
}
```
