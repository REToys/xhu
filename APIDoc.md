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


> 太多了, 以后再写...

--- 

## 成员 / Members 

--- 

## 想法 / Pins

--- 

## 专栏 / Columns
