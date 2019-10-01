# xhu

> 运行在 [`Cloudflare Workers`](https://workers.dev) 上面的 `*乎` 的 API.

## API 文档

> [**点击查看文档**](./APIDoc.md)

> [**点击查看 test.http (VSCode + Rest Client 打开可以测试)**](./test.http) 


## 域名和限制 

在 [`Cloudflare Workers`](https://workers.dev) 申请的子域为 `zhihuvvv.workers.dev`, 是对 [`zhihuvvv`](http://zhihuvvv.com) 的致敬.

而关于 [`Cloudflare Workers Free`](https://workers.dev) 的 [**限制**](https://developers.cloudflare.com/workers/about/limits/) 为 ( `zhihuvvv.workers.dev` 子域全局):

1. 1000 requests per 10 minutes / 十分钟内一千次请求
2. 100,000 requests per day / 每天十万次请求


## 动机 

众所周知, `*乎` 对于移动版网页 (包括微信小程序) 的限制非常苛刻, 苛刻到无法使用的地步, 体现在: 

1. 无法查看第一个回答之外的全文 (如果内容稍长的话)
2. 无法查看所有评论
3. 无法点击回答者的头像进入 Ta 的个人主页
4. 大段的广告, 底部则是大量的推荐问题
5. ...

总之就是想着法子引导移动端用户下载 app. 

而如果真的安装了 app, 拉起之后, 则会被记录浏览习惯, 所以可能一个无心的点击就会影响个性化推荐.

Android 版推出了 `极速版` , 但是有功能限制, 而且设计得更多像是 `*乎` 在探路短视频.

曾经在 [`v2ex`](https://www.v2ex.com/t/520509) 看见一个作品叫做 [**zhihuvvv**](http://zhihuvvv.com), 利用 `*乎` 给予搜索引擎的优待, 不过似乎已经失效很久. 

在一次群内谈论 [`Cloudflare Workers`](https://workers.dev) 的过程中, 于是就想能不能利用 [`Cloudflare Workers`](https://workers.dev) 来 `复活` 这个项目.  

于是开始了分析. 

## 分析  

[`zhihuvvv`](http://zhihuvvv.com) 的思路应该是被针对了, 所以考虑自己实现. 

首先考虑的是桌面版 API, 抓包可以看到是 `zhihu.com/v4` 这样的 API, 从 [`RSSHub`](https://docs.rsshub.app/social-media.html#%E7%9F%A5%E4%B9%8E) 来看, 有较严格的反爬. 且经过测试, 很多问题必须要登录账号才能获取. 

于是考虑不需要登录账号就可以查看这类问题的 Android 版本, 逆向自然是尽量看逻辑简单的, 所以首先分析极速版. 

极速版用 flutter 实现, 加了梆梆的壳, 总的来说逻辑肯定要比正式版简单, 但是在分析过程中发现了使用限制, 例如不能查看问题的评论和关注列表等等. 当然这种限制也有可能不是 API 层面的, 但是考虑到很多公司类似极速版的产品都"不得善终", 所以为了维护方便计, 还是决定从正式版下手. 

正式版 APP 的 API 功能相当齐全, 只有一个例外: `问题日志` . 但是这个一直没有找到 API, 官方无论是桌面还是移动端也都是直接返回 html, 且必须要登录 (需要名为 `q_c0` 的 cookie). 

## 开源 

目前有两个问题: 

1. 这类逆向的代码虽然简单, 但是开源的风险性不知如何 
2. 不擅长正向开发, 近期学一下规范, 将代码整规范些再行开源/捂脸  


## TODO 
 
- ~~实现 API~~ 
- 整理开源
- 实现类似 [`zhihuvvv`](http://zhihuvvv.com) 的跳转 "去限制" (前端实在苦手, 希望有感兴趣的朋友一起完成, 我觉得完全可以做得比 app 还好使哇: 免安装免登录免广告免打扰免追踪, 除了需要登录账号的个性化和问题日志, 功能需要的数据基本都能拿到)


