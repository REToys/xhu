# API 文档

## 注册

> 这个所谓 `注册` 其实是对应 app 的设备注册 token, 会自动随机生成, 存放在子域名的 Cookie 中, 暂时设定 expired 时间是三天. 所以请求的时候需要带上 Cookie.

### 获取 udid

> 为了和 app 保持一致, 唯独它的域名用的是 `appcloud.zhihuvvv.workers.dev`.

> 成功会设置 `.zhihuvvv.workers.dev` 的 Cookie, 如果 Cookie 未失效则直接返回.

#### Request
- Method: **GET**
- URL:  `/v1/device`


#### Response  

- Body  
```json
{
  "udid": "A****************************-****0=",
  "sn": "7**************6"
}
```


### 获取 token

> 接下来所有域名都是 `api.zhihuvvv.workers.dev`.

> 成功会设置 `.zhihuvvv.workers.dev` 的 Cookie, 如果 Cookie 未失效则直接返回.

#### Request
- Method: **GET**
- URL:  `/guests/token`


#### Response  

- Body  
```json
{
  "udid": "A****************************-****0=",
  "access_token": "gt2.**************************************************************g=="
}
```

--- 

## 问题 / Questions

### 问题概览

#### Request
- Method: **GET**
- URL:  `/questions/:questionId`
    - `questionId`: 问题 ID, 例如 `264051433`


#### Response  

- Body  
```json

```


### 回答列表

> 多页的返回 json 中一般都会有 `paging`, 会有 `is_end`, `totals`, `is_start`, `next`, `previous` 之类的字段以供翻页, 也是推荐做法, 因为有些似乎无法计算下一页的参数.



#### Request
- Method: **GET**
- URL:  `/questions/:questionId/answers?limit={limit}&offset={offset}&order_by={order_by}`
    - `questionId`: 问题 ID, 例如 `264051433`
    - `limit`: 限制每次返回的数量
    - `offset`: 偏移
    - `order_by`: 留空为默认排序, `created` 为按时间倒序


#### Response  

- Body  
```json

```


### 问题关注列表

#### Request
- Method: **GET**
- URL:  `/questions/:questionId/followers?limit={limit}&offset={offset}`
    - `questionId`: 问题 ID, 例如 `264051433`
    - `limit`: 限制每次返回的数量
    - `offset`: 偏移


#### Response  

- Body  
```json

```


### 问题评论列表

#### Request
- Method: **GET**
- URL:  `/questions/:questionId/comments?limit={limit}&offset={offset}&reverse_order={reverse_order}`
    - `questionId`: 问题 ID, 例如 `264051433`
    - `limit`: 限制每次返回的数量
    - `offset`: 偏移
    - `reverse_order`: 是否倒序 (其实就是按时间排序), `false` / `true`


#### Response  

- Body  
```json

```

--- 

## 回答 / Answers

### 回答评论列表

#### Request
- Method: **GET**
- URL:  `/answers/:answerId/comments?limit={limit}&offset={offset}&reverse_order={reverse_order}&status={status}`
    - `answerId`: 回答 ID, 例如 `794739996`
    - `limit`: 限制每次返回的数量
    - `offset`: 偏移
    - `reverse_order`: 是否倒序 (其实就是按时间排序), `false` / `true`
    - `status`: 我也没测是啥, 取值默认是 `open` , 猜测是折叠? 


#### Response  

- Body  
```json

```


--- 

## 评论 / Comments

### 评论回复列表

#### Request
- Method: **GET**
- URL:  `/comments/:commentId/replies?limit={limit}&offset={offset}`
    - `commentId`: 评论 ID, 例如 `719420817`
    - `limit`: 限制每次返回的数量
    - `offset`: 偏移


#### Response  

- Body  
```json

```


### 评论对话列表

#### Request
- Method: **GET**
- URL:  `/comments/:commentId/conversation?limit={limit}&offset={offset}`
    - `commentId`: 评论 ID, 例如 `553635986`
    - `limit`: 限制每次返回的数量
    - `offset`: 偏移


#### Response  

- Body  
```json

```

--- 

## 个人 / People

### 个人概览

#### Request
- Method: **GET**
- URL:  `/people/:peopleId`
    - `peopleId`: 个人 ID, 例如 `7baaf3c00c2c7daeddf8e9ba813af141`


#### Response  

- Body  
```json

```


### 动态列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/activities?before_id={before_id}&limit={limit}&session_id={session_id}&desktop={desktop}`
    - `peopleId`: 个人 ID, 例如 `7baaf3c00c2c7daeddf8e9ba813af141`
    - `limit`: 限制每次返回的数量
    - `before_id`: 
    - `session_id`: 
    - `desktop`: 


#### Response  

- Body  
```json

```


### 回答列表

### 提问列表

### 文章列表

### 专栏列表

### 想法列表

### 收藏列表

### 关注列表

### 粉丝列表

### Live 列表

### 关注的专栏列表

### 关注的问题列表

### 关注的话题列表

### 关注的收藏夹列表

### 表情包列表 (猜测 self 可以换为 peopleId, 自测)

#### Request
- Method: **GET**
- URL:  `/people/self/sticker-groups`


#### Response  

- Body  
```json

```

--- 

## Live / Lives 

### Live 概览


--- 

## 成员 / Members 

### 成员被收录的回答

### 成员被收录的文章

### 成员的形象标签

### 成员的形象标签附议人



--- 

## 想法 / Pins

### 想法概览

### 想法转发评论鼓掌数

### 想法被转发和鼓掌动态列表

### 想法评论列表

### 想法评论的楼中楼

### 想法热榜

### 想法推荐

### 想法热榜有无更新

### 想法推荐用户?

### 个人想法列表

### 个人关注的想法专栏

### 想法专栏概览

### 想法专栏列表

### 想法专栏是否有更新



--- 

## 专栏 / Columns

### 专栏概览

#### Request
- Method: **GET**
- URL:  `/columns/:columnId?include=$.intro`
    - `columnId`: 专栏 ID, 例如 `duku66`



#### Response  

- Body  
```json

```

### 专栏置顶文章(未测试)

#### Request
- Method: **GET**
- URL:  `/columns/:columnId/pinned-article`
    - `columnId`: 专栏 ID, 例如 `duku66`



#### Response  

- Body  
```json

```



### 专栏文章列表

#### Request
- Method: **GET**
- URL:  `/columns/:columnId/articles?include=data[*].label_info&limit={limit}&offset={offset}&member_hash={member_hash}`
    - `columnId`: 专栏 ID, 例如 `duku66`
    - `limit`: 限制每次返回的数量
    - `offset`: 偏移
    - `member_hash`: 自测


#### Response  

- Body  
```json

```


### 专栏编辑者列表

#### Request
- Method: **GET**
- URL:  `/columns/:columnId/coauthors?limit={limit}&offset={offset}`
    - `columnId`: 专栏 ID, 例如 `duku66`
    - `limit`: 限制每次返回的数量
    - `offset`: 偏移


#### Response  

- Body  
```json

```



### 专栏关注者列表

#### Request
- Method: **GET**
- URL:  `/columns/:columnId/followers?limit={limit}&offset={offset}`
    - `columnId`: 专栏 ID, 例如 `duku66`
    - `limit`: 限制每次返回的数量
    - `offset`: 偏移


#### Response  

- Body  
```json

```

---

## 搜索 / Search

### 热搜标签

#### Request
- Method: **GET**
- URL:  `/search/top_search/tabs`


#### Response  

- Body  
```json

```


### 热搜词

#### Request
- Method: **GET**
- URL:  `/search/top_search/tabs/hot/items`


#### Response  

- Body  
```json

```

### 标签下的热搜词

#### Request
- Method: **GET**
- URL:  `/search/top_search/tabs/:tabName/items`
    - `tabName`: 标签名, 例如 `hot`, `hello`


#### Response  

- Body  
```json

```


### 预热搜 (也就是出现在 app 刚打开的搜索栏)

#### Request
- Method: **GET**
- URL:  `/search/preset_words?w=%5B%5D`


#### Response  

- Body  
```json

```


### 搜索建议

#### Request
- Method: **GET**
- URL:  `/search/suggest?q={keyword}&magi=1`
    - `keyword`: 关键词


#### Response  

- Body  
```json

```


### 搜索关键词

#### Request
- Method: **GET**
- URL:  `/search?q={keyword}&t={type}&lc_idx=0&correction=1&offset=0&advert_count=0&limit=20&magi=false&is_real_time={is_real_time}&show_all_topics=0`
    - `keyword`: 关键词
    - `type`: 类型, `综合=generic`, `用户=people`, `话题=topic`, `盐选专栏=album`, `Live=live`, `电子书=publication`, `专栏=column`, `想法=pin`
    - `is_real_time`: 0 代表所有, 1 代表最近一周


#### Response  

- Body  
```json

```


---

## 热榜 / topstory

### 热榜列表

#### Request
- Method: **GET**
- URL:  `/topstory/hot-list?limit={limit}`
    - `limit`: 限制每次返回的数量


#### Response  

- Body  
```json

```

### 热榜视频

#### Request
- Method: **GET**
- URL:  `/topstory/selected_videos?action=up&offset={offset}&count={count}&session_token=`
    - `count`: 每次返回的数量
    - `offset`: 偏移    


#### Response  

- Body  
```json

```



### 热榜推荐

#### Request
- Method: **GET**
- URL:  `/topstory/recommend?action=down&scroll=up&limit={limit}&start_type=warm`
    - `limit`: 限制每次返回的数量  


#### Response  

- Body  
```json

```

--- 

## 话题 / Topics

### 话题概览

#### Request
- Method: **GET**
- URL:  `/topics/:topicId/basic`
    - `topicId`: 话题 ID, 例如 `19566035`  


#### Response  

- Body  
```json

```


### 话题动态

#### Request
- Method: **GET**
- URL:  `/topics/:topicId/feeds/top_activity?before_id=0&limit=1`
    - `topicId`: 话题 ID, 例如 `19566035`  


#### Response  

- Body  
```json

```

### 话题全部问题

### 话题精华列表目录/章节

### 话题精华列表

--- 

## 文章 / Articles

### 文章概览

### 文章评论列表

### 文章评论的楼中楼

--- 

## 收藏夹 / Collections

### 收藏夹概览

### 收藏夹内容列表

### 收藏夹关注列表


--- 

> 太多了, 有些省略没写了, 慢慢补上... 也可以对照 `test.http` 来测试和猜测. 缺什么功能可以自行抓包拼凑尝试, 或者提 issue.