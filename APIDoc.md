# API 文档

Table of Contents
=================

   * [API 文档](#api-文档)
   * [Table of Contents](#table-of-contents)
      * [域名](#域名)
      * [注册](#注册)
         * [获取 udid](#获取-udid)
         * [获取 token](#获取-token)
      * [问题 / Questions](#问题--questions)
         * [问题概览](#问题概览)
         * [回答列表](#回答列表)
         * [问题关注列表](#问题关注列表)
         * [问题评论列表](#问题评论列表)
      * [回答 / Answers](#回答--answers)
         * [回答评论列表](#回答评论列表)
      * [评论 / Comments](#评论--comments)
         * [评论回复列表](#评论回复列表)
         * [评论对话列表](#评论对话列表)
      * [个人 / People](#个人--people)
         * [个人概览](#个人概览)
         * [动态列表](#动态列表)
         * [Live 统计](#live-统计)
         * [Market 统计](#market-统计)
         * [Market 概览](#market-概览)
         * [回答列表](#回答列表-1)
         * [提问列表](#提问列表)
         * [文章列表](#文章列表)
         * [专栏列表](#专栏列表)
         * [收藏夹列表](#收藏夹列表)
         * [Live 列表](#live-列表)
         * [关注列表](#关注列表)
         * [粉丝列表](#粉丝列表)
         * [关注的专栏列表](#关注的专栏列表)
         * [关注的问题列表](#关注的问题列表)
         * [关注的话题列表](#关注的话题列表)
         * [关注的收藏夹列表](#关注的收藏夹列表)
         * [表情包列表 (猜测 self 可以换为 peopleId, 自测)](#表情包列表-猜测-self-可以换为-peopleid-自测)
      * [Live / Lives](#live--lives)
         * [Live 概览](#live-概览)
      * [成员 / Members](#成员--members)
         * [成员被收录的回答](#成员被收录的回答)
         * [成员被收录的文章](#成员被收录的文章)
         * [成员的形象标签](#成员的形象标签)
         * [成员的形象标签支持者](#成员的形象标签支持者)
      * [想法 / Pins](#想法--pins)
         * [想法热榜](#想法热榜)
         * [想法推荐](#想法推荐)
         * [想法热榜有无更新](#想法热榜有无更新)
         * [想法推荐用户?](#想法推荐用户)
         * [想法概览](#想法概览)
         * [想法转发评论鼓掌数](#想法转发评论鼓掌数)
         * [想法被转发和鼓掌动态列表](#想法被转发和鼓掌动态列表)
         * [想法评论列表](#想法评论列表)
         * [想法评论的楼中楼](#想法评论的楼中楼)
         * [个人想法列表](#个人想法列表)
         * [个人关注的想法专栏 (标签)](#个人关注的想法专栏-标签)
         * [想法专栏概览](#想法专栏概览)
         * [想法专栏列表](#想法专栏列表)
         * [想法专栏是否有更新](#想法专栏是否有更新)
      * [专栏 / Columns](#专栏--columns)
         * [专栏概览](#专栏概览)
         * [专栏置顶文章(未测试)](#专栏置顶文章未测试)
         * [专栏文章列表](#专栏文章列表)
         * [专栏编辑者列表](#专栏编辑者列表)
         * [专栏关注者列表](#专栏关注者列表)
      * [搜索 / Search](#搜索--search)
         * [热搜标签](#热搜标签)
         * [热搜词](#热搜词)
         * [标签下的热搜词](#标签下的热搜词)
         * [预热搜 (也就是出现在 app 刚打开的搜索栏)](#预热搜-也就是出现在-app-刚打开的搜索栏)
         * [搜索建议](#搜索建议)
         * [搜索关键词](#搜索关键词)
      * [热榜 / topstory](#热榜--topstory)
         * [热榜列表](#热榜列表)
         * [热榜视频](#热榜视频)
         * [热榜推荐](#热榜推荐)
      * [话题 / Topics](#话题--topics)
         * [话题概览](#话题概览)
         * [话题动态](#话题动态)
         * [话题全部问题列表](#话题全部问题列表)
         * [话题未回答问题列表](#话题未回答问题列表)
         * [话题精华目录/章节](#话题精华目录章节)
         * [话题精华列表](#话题精华列表)
      * [文章 / Articles](#文章--articles)
         * [文章概览](#文章概览)
         * [文章评论列表](#文章评论列表)
         * [文章评论的楼中楼](#文章评论的楼中楼)
      * [收藏夹 / Collections](#收藏夹--collections)
         * [收藏夹概览](#收藏夹概览)
         * [收藏夹内容列表](#收藏夹内容列表)
         * [收藏夹关注列表](#收藏夹关注列表)
---


## 域名

域名均为 **`api.zhihuvvv.workers.dev`**

## 注册

> 这个所谓 `注册` 其实是对应 app 的设备注册 token, 会自动随机生成, 存放在子域名的 Cookie 中, 暂时设定 expired 时间是三天. 所以请求的时候 **必须** 要带上 Cookie.

### 获取 udid

> 成功会设置 `.zhihuvvv.workers.dev` 的 Cookie, 如果 Cookie 未失效则直接返回.

#### Request
- Method: **GET**
- URL:  `/appcloud/v1/device`


#### Response  

- Body  
```json
{
  "udid": "A****************************-****0=",
  "sn": "7**************6"
}
```


### 获取 token

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
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```


### 动态列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/activities?before_id={before_id}&limit={limit}&session_id={session_id}&desktop={desktop}`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`
    - `limit`: 限制每次返回的数量
    - `before_id`: 
    - `session_id`: 
    - `desktop`: 


#### Response  

- Body  
```json

```

### Live 统计

#### Request
- Method: **GET**
- URL:  `/lives/people/:peopleId/statistics`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```

### Market 统计

#### Request
- Method: **GET**
- URL:  `/market/people/:peopleId/statistics`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```

### Market 概览

#### Request
- Method: **GET**
- URL:  `/market/people/:peopleId/works/summary`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```

### 回答列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/answers?limit=20&order_by={order_by}&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`
    - `order_by`: `按时间排序=created`, `按赞数排序=votenum`

#### Response  

- Body  
```json

```

### 提问列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/questions?limit=20&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`

#### Response  

- Body  
```json

```

### 文章列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/articles?limit=20&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```

### 专栏列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/columns?limit=20&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```


### 收藏夹列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/collections_v2?limit=20&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```

### Live 列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/lives?limit=10&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```

### 关注列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/followees?limit=20&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```

### 粉丝列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/followers?limit=20&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```

### 关注的专栏列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/following_columns?limit=20&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```

### 关注的问题列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/following-questions?limit=20&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```

### 关注的话题列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/following_topics?limit=20&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```

### 关注的收藏夹列表

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/following_collections?limit=20&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`


#### Response  

- Body  
```json

```

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

#### Request
- Method: **GET**
- URL:  `/lives/:liveId`
    - `liveId`: Live ID, 例如 `820225868382216192`



#### Response  

- Body  
```json

```


--- 

## 成员 / Members 

### 成员被收录的回答

#### Request
- Method: **GET**
- URL:  `/members/:memberId/marked-answers?per_page=20&limit=10&offset=0`
    - `memberId`: 成员 ID, 有别于 peopleId, 例如 `yuxinlie`, 自测


#### Response  

- Body  
```json

```

### 成员被收录的文章

#### Request
- Method: **GET**
- URL:  `/people/:peopleId/included-articles?offset=20&limit=20&sort_by={sort_by}`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`
    - `sort_by`: `按时间=created`, `按赞数=vote_num`


#### Response  

- Body  
```json

```

### 成员的形象标签

#### Request
- Method: **GET**
- URL:  `/api/v4/members/:memberId/signalments`
    - `memberId`: 成员 ID, 有别于 peopleId, 例如 `yuxinlie`, 自测


#### Response  

- Body  
```json

```

### 成员的形象标签支持者

#### Request
- Method: **GET**
- URL:  `/api/v4/members/:memberId/signalments/:signalmentId/voters?offset=0`
    - `memberId`: 成员 ID, 有别于 peopleId, 例如 `yuxinlie`, 自测
    - `signalmentId`: 形象标签 ID, 例如 `942770846528507904`

#### Response  

- Body  
```json

```



--- 

## 想法 / Pins

### 想法热榜

#### Request
- Method: **GET**
- URL:  `/pins/hot_list`



#### Response  

- Body  
```json

```

### 想法推荐

#### Request
- Method: **GET**
- URL:  `/pins/moments`



#### Response  

- Body  
```json

```

### 想法热榜有无更新

#### Request
- Method: **GET**
- URL:  `/pins/check_update`



#### Response  

- Body  
```json

```

### 想法推荐用户?

#### Request
- Method: **GET**
- URL:  `/pins/recommend/relation_member/hint`



#### Response  

- Body  
```json

```

### 想法概览

#### Request
- Method: **GET**
- URL:  `/pins/:pinId`
    - `pinId`: 想法 ID, 例如 `1143178555272941568`



#### Response  

- Body  
```json

```

### 想法转发评论鼓掌数

#### Request
- Method: **GET**
- URL:  `/pins/interaction_count?pin_ids={pin_ids}`
    - `pin_ids`: 多个想法 ID



#### Response  

- Body  
```json

```

### 想法被转发和鼓掌动态列表

#### Request
- Method: **GET**
- URL:  `/pins/:pinId/actions?limit=20&offset=0`
    - `pinId`: 想法 ID, 例如 `1143178555272941568`



#### Response  

- Body  
```json

```

### 想法评论列表

#### Request
- Method: **GET**
- URL:  `/pins/:pinId/root_comments?limit=20&offset=0`
    - `pinId`: 想法 ID, 例如 `1143178555272941568`



#### Response  

- Body  
```json

```

### 想法评论的楼中楼

#### Request
- Method: **GET**
- URL:  `/comments/:commentId/child_comments?order=ascending&offset=0&limit=20&order=ascending`
    - `commentId`: 评论 ID, 例如 `710344086`



#### Response  

- Body  
```json

```

### 个人想法列表

#### Request
- Method: **GET**
- URL:  `/pins/:peopleId/moments`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`



#### Response  

- Body  
```json

```

### 个人关注的想法专栏 (标签)

#### Request
- Method: **GET**
- URL:  `/pins/:peopleId/following_specials?limit=10&offset=0`
    - `peopleId`: 个人 ID, 例如 `246e6cf44e94cefbf4b959cb5042bc91`



#### Response  

- Body  
```json

```

### 想法专栏概览

#### Request
- Method: **GET**
- URL:  `/pins/special/:specialpinId`
    - `specialpinId`: 想法专栏 ID, 例如 `972884951192113152`



#### Response  

- Body  
```json

```

### 想法专栏列表

#### Request
- Method: **GET**
- URL:  `/pins/special/:specialpinId/moments?order_by={order_by}&hottest_moment_source=hot&limit=10&offset=0`
    - `specialpinId`: 想法专栏 ID, 例如 `972884951192113152`
    - `order_by`: `最热=hottest`, `最新=newest`



#### Response  

- Body  
```json

```

### 想法专栏是否有更新

#### Request
- Method: **GET**
- URL:  `/pins/special/:specialpinId/check_update?timestamp={timestamp}`
    - `specialpinId`: 想法专栏 ID, 例如 `972884951192113152`
    - `timestamp`: 指定时间, 例如 `1569956209`



#### Response  

- Body  
```json

```



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

### 话题全部问题列表

#### Request
- Method: **GET**
- URL:  `/topics/:topicId/feeds/top_activity?before_id=0&limit=10`
    - `topicId`: 话题 ID, 例如 `19566035`  


#### Response  

- Body  
```json

```

### 话题未回答问题列表

#### Request
- Method: **GET**
- URL:  `/topics/:topicId/unanswered_questions?offset=0&limit=10`
    - `topicId`: 话题 ID, 例如 `19566035`  


#### Response  

- Body  
```json

```


### 话题精华目录/章节


#### Request
- Method: **GET**
- URL:  `/topics/:topicId/topic_index`
    - `topicId`: 话题 ID, 例如 `19566035`  


#### Response  

- Body  
```json

```

### 话题精华列表


#### Request
- Method: **GET**
- URL:  `/topics/:topicId/essence_feeds?offset=0&limit=10`
    - `topicId`: 话题 ID, 例如 `19566035`  


#### Response  

- Body  
```json

```

--- 

## 文章 / Articles

### 文章概览

#### Request
- Method: **GET**
- URL:  `/articles/:articleId`
    - `articleId`: 文章 ID, 例如 `21463284`  


#### Response  

- Body  
```json

```

### 文章评论列表

#### Request
- Method: **GET**
- URL:  `/articles/:articleId/root_comments?limit=10&offset=0&reverse_order=false`
    - `articleId`: 文章 ID, 例如 `21463284`  


#### Response  

- Body  
```json

```

### 文章评论的楼中楼

#### Request
- Method: **GET**
- URL:  `/comments/:commentId/child_comments?order=ascending&offset=0&limit=20&order=ascending`
    - `commentId`: 评论 ID, 例如 `146547958`  


#### Response  

- Body  
```json

```

--- 

## 收藏夹 / Collections

### 收藏夹概览

#### Request
- Method: **GET**
- URL:  `/collections/:collectionId`
    - `collectionId`: 收藏夹 ID, 例如 `20948311`  


#### Response  

- Body  
```json

```

### 收藏夹内容列表

#### Request
- Method: **GET**
- URL:  `/collections/:collectionId/contents?limit=20&offset=0`
    - `collectionId`: 收藏夹 ID, 例如 `20948311`  


#### Response  

- Body  
```json

```

### 收藏夹关注列表

#### Request
- Method: **GET**
- URL:  `/collections/:collectionId/followers?limit=20&offset=0`
    - `collectionId`: 收藏夹 ID, 例如 `20948311`  


#### Response  

- Body  
```json

```


--- 

> 太多了, 可能有些没写进去, 尽量慢慢补上... 也可以对照 `test.http` 来测试和猜测. 或者自行抓包尝试, 或者提 issue.