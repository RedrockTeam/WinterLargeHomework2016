# 挑战

+ 做的好的有奖励


+ 完成这个挑战你所需要的姿势: 

  - HTML
  - CSS
  - DOM
  - BOM
  - AJAX
  - JSON

+ 实现 github profile 页面 example: [github-GiantMing](https://github.com/giantming) 功能点:

  - 页面布局
  - 左边栏用户信息: 头像, 用户名, 介绍, 组织等动态数据
  - Overview
  - Repositories, 
  - Stars, 
  - Follwers, 
  - Following

+ 提示: 

  举个栗子: 

  小明用完成了这个挑战, 用户主页的 html 名为 `github-profile.html`, 他把这个页面发给了大明, 大明在把`github-profile.html`放到服务器环境下

  浏览器请求 `localhost/github-profile.html?user=giantming`, 显示出了用户 `giantming` 的 `github` 用户页面.

  小明可能是这样实现的: 

  1. 获取get 参数中的 user 字段, 即在本例中的 `giantming`

  2. 拿到用户名以后根据用户名 ajax 请求 github 的 api 接口 求`https://api.github.com/users/giantming` 请求method为get 

     (注: github 的 API 接口均开放了跨域请求)

      拿到了以下信息: 

  ```javascript
  {
    "login": "GiantMing",  // 用户名
    "id": 10388989,
    "avatar_url": "https://avatars.githubusercontent.com/u/10388989?v=3", // 头像
    "gravatar_id": "",
    "url": "https://api.github.com/users/GiantMing", 
    "html_url": "https://github.com/GiantMing",
    "followers_url": "https://api.github.com/users/GiantMing/followers",
    "following_url": "https://api.github.com/users/GiantMing/following{/other_user}",
    "gists_url": "https://api.github.com/users/GiantMing/gists{/gist_id}",
    "starred_url": "https://api.github.com/users/GiantMing/starred{/owner}{/repo}",
    "subscriptions_url": "https://api.github.com/users/GiantMing/subscriptions",
    "organizations_url": "https://api.github.com/users/GiantMing/orgs",
    "repos_url": "https://api.github.com/users/GiantMing/repos",
    "events_url": "https://api.github.com/users/GiantMing/events{/privacy}",
    "received_events_url": "https://api.github.com/users/GiantMing/received_events",
    "type": "User",
    "site_admin": false,
    "name": "Ming",
    "company": "重庆邮电大学",
    "blog": "http://todoit.me",
    "location": "重庆市崇文路二号",
    "email": "Giantming@outlook.com",
    "hireable": true,
    "bio": "@RedrockTeam ",
    "public_repos": 34,
    "public_gists": 0,
    "followers": 11,
    "following": 20,
    "created_at": "2015-01-04T11:51:14Z",
    "updated_at": "2016-12-09T13:38:00Z"
  }
  ```

  然后根据返回的 json 数据再分别请求其他数据, 如

  - organizations
  - followers 
  - followering
  - …..

+ 本题涉及到很多 ajax 请求, json 数据处理, 

+ 请使用 异步的 ajax请求

+ 那么多 异步 ajax 请求, 如何避免回调炼狱?

参考:

[github开发者api文档](developer.github.com/v3)

[MDN ajax 入门](https://developer.mozilla.org/zh-CN/docs/AJAX/Getting_Started)