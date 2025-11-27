# Twitter241 MCP Server

[English](./README_EN.md) | 简体中文 | [繁體中文](./README_ZH-TW.md)

## 🚀 使用 EMCP 平台快速体验

**[EMCP](https://sit-emcp.kaleido.guru)** 是一个强大的 MCP 服务器管理平台，让您无需手动配置即可快速使用各种 MCP 服务器！

### 快速开始：

1. 🌐 访问 **[EMCP 平台](https://sit-emcp.kaleido.guru)**
2. 📝 注册并登录账号
3. 🎯 进入 **MCP 广场**，浏览所有可用的 MCP 服务器
4. 🔍 搜索或找到本服务器（`bach-twitter241`）
5. 🎉 点击 **"安装 MCP"** 按钮
6. ✅ 完成！即可在您的应用中使用

### EMCP 平台优势：

- ✨ **零配置**：无需手动编辑配置文件
- 🎨 **可视化管理**：图形界面轻松管理所有 MCP 服务器
- 🔐 **安全可靠**：统一管理 API 密钥和认证信息
- 🚀 **一键安装**：MCP 广场提供丰富的服务器选择
- 📊 **使用统计**：实时查看服务调用情况

立即访问 **[EMCP 平台](https://sit-emcp.kaleido.guru)** 开始您的 MCP 之旅！


---

## 简介

这是一个 MCP 服务器，用于访问 Twitter241 API。

- **PyPI 包名**: `bach-twitter241`
- **版本**: 1.0.0
- **传输协议**: stdio


## 安装

### 从 PyPI 安装:

```bash
pip install bach-twitter241
```

### 从源码安装:

```bash
pip install -e .
```

## 运行

### 方式 1: 使用 uvx（推荐，无需安装）

```bash
# 运行（uvx 会自动安装并运行）
uvx --from bach-twitter241 bach_twitter241

# 或指定版本
uvx --from bach-twitter241@latest bach_twitter241
```

### 方式 2: 直接运行（开发模式）

```bash
python server.py
```

### 方式 3: 安装后作为命令运行

```bash
# 安装
pip install bach-twitter241

# 运行（命令名使用下划线）
bach_twitter241
```

## 配置

### API 认证

此 API 需要认证。请设置环境变量:

```bash
export API_KEY="your_api_key_here"
```

### 环境变量

| 变量名 | 说明 | 必需 |
|--------|------|------|
| `API_KEY` | API 密钥 | 是 |
| `PORT` | 不适用 | 否 |
| `HOST` | 不适用 | 否 |



### 在 Claude Desktop 中使用

编辑 Claude Desktop 配置文件 `claude_desktop_config.json`:


```json
{
  "mcpServers": {
    "twitter241": {
      "command": "uvx",
      "args": ["--from", "bach-twitter241", "bach_twitter241"],
      "env": {
        "API_KEY": "your_api_key_here"
      }
    }
  }
}
```

**注意**: 请将 `E:\path\to\twitter241\server.py` 替换为实际的服务器文件路径。


## 可用工具

此服务器提供以下工具:


### `get_about_account`

Get About Account

**端点**: `GET /about-account`


**参数**:

- `username` (string) *必需*: Example value: MrBeast



---


### `get_community_details`

Get Community Details by Community ID

**端点**: `GET /community-details`


**参数**:

- `communityId` (string) *必需*: Example value: 1601841656147345410



---


### `get_community_about`

Get Community About by Community Id

**端点**: `GET /community-about`


**参数**:

- `communityId` (string) *必需*: Example value: 1601841656147345410



---


### `get_community_tweets`

Get Community Tweets by Community ID

**端点**: `GET /community-tweets`


**参数**:

- `communityId` (string) *必需*: Example value: 1601841656147345410

- `searchType` (string) *必需*: Default or Media

- `rankingMode` (string): Relevance or Recency or Likes

- `count` (string): Example value: 20

- `cursor` (string): Example value: 



---


### `get_community_moderators`

Get Community Moderators by Community ID

**端点**: `GET /community-moderators`


**参数**:

- `communityId` (string) *必需*: Example value: 1601841656147345410

- `cursor` (string): Example value: 



---


### `get_community_timeline`

Explore Community Timeline

**端点**: `GET /explore-community-timeline`


**参数**:

- `topicId` (string) *必需*: Example value: 4

- `cursor` (string): Example value: 



---


### `get_community_topics`

Get Community Topics

**端点**: `GET /community-topics`



---


### `fetch_popular_community`

Fetch Popular Community

**端点**: `GET /fetch-popular-community`


**参数**:

- `topicId` (string) *必需*: Get this value from GET /community-topics

- `count` (string) *必需*: Example value: 20

- `cursor` (string): Example value: 



---


### `search_community`

Search community

**端点**: `GET /search-community`


**参数**:

- `query` (string) *必需*: Example value: football

- `count` (string) *必需*: Example value: 20

- `cursor` (string): Example value: 



---


### `get_community_members`

Get Community Members by Community ID

**端点**: `GET /community-members`


**参数**:

- `communityId` (string) *必需*: Example value: 1601841656147345410

- `cursor` (string): Example value: 



---


### `get_tweet_details`

Get Tweet Details By Tweet ID

**端点**: `GET /tweet`


**参数**:

- `pid` (string) *必需*: Example value: 1631781099415257088



---


### `get_post_comments_v2`

Get Post Comments By Post ID V2

**端点**: `GET /comments-v2`


**参数**:

- `pid` (string) *必需*: Example value: 1924185704613208381

- `rankingMode` (string): Relevance || Likes || Recency

- `count` (string): Example value: 20

- `cursor` (string): Example value: 



---


### `get_list_details`

Get list details by listId

**端点**: `GET /list-details`


**参数**:

- `listId` (string) *必需*: Get this value from \\\"lists[x].object_id\\\" returned from GET /search-lists Endpoint



---


### `get_list_timeline`

Get list timeline by listId

**端点**: `GET /list-timeline`


**参数**:

- `listId` (string) *必需*: Get this value from \\\"lists[x].object_id\\\" returned from GET /search-lists Endpoint

- `cursor` (string): Example value: 



---


### `search_lists`

Search lists

**端点**: `GET /search-lists`


**参数**:

- `query` (string) *必需*: Example value: football



---


### `get_highlights`

Get user highlights by ID

**端点**: `GET /highlights`


**参数**:

- `user` (string) *必需*: Example value: 877807935493033984

- `count` (string) *必需*: Example value: 20

- `cursor` (string): Example value: 



---


### `get_user_followers_ids`

GET Followers IDs by Username

**端点**: `GET /followers-ids`


**参数**:

- `username` (string) *必需*: Example value: mrbeast

- `count` (string) *必需*: Maximum count is 5000

- `cursor` (string): Example value: 



---


### `get_user_verified_followers`

Get User Verified Followers By ID.   You can get the user(rest_id) query from \

**端点**: `GET /verified-followers`


**参数**:

- `user` (string) *必需*: Example value: 877807935493033984

- `count` (string) *必需*: Example value: 20

- `cursor` (string): Example value: 



---


### `get_user_following_ids`

GET Following IDs by Username

**端点**: `GET /following-ids`


**参数**:

- `username` (string) *必需*: Example value: mrbeast

- `count` (string) *必需*: Maximum count is 5000

- `cursor` (string): Example value: 



---


### `get_user_followers`

Get User Followers By ID.   You can get the user(rest_id) query from \

**端点**: `GET /followers`


**参数**:

- `cursor` (string): Example value: 

- `user` (string) *必需*: Example value: 2455740283

- `count` (string) *必需*: Example value: 20



---


### `get_user_followings`

Get User Followings By ID.   You can get the user(rest_id) query from \

**端点**: `GET /followings`


**参数**:

- `cursor` (string): Example value: 

- `user` (string) *必需*: Example value: 2455740283

- `count` (string) *必需*: Example value: 20



---


### `get_user_tweets`

Get User Tweets By ID  You can get the user(rest_id) query from \

**端点**: `GET /user-tweets`


**参数**:

- `user` (string) *必需*: Example value: 2455740283

- `count` (string) *必需*: Example value: 20

- `cursor` (string): Example value: 



---


### `get_user_media`

Get User Media By ID  You can get the user(rest_id) query from \

**端点**: `GET /user-media`


**参数**:

- `user` (string) *必需*: Example value: 2455740283

- `count` (string) *必需*: Example value: 20

- `cursor` (string): Example value: 



---


### `get_user_replies_v2`

Get User Replies By ID  You can get the user(rest_id) query from \

**端点**: `GET /user-replies-v2`


**参数**:

- `user` (string) *必需*: Example value: 2455740283

- `count` (string) *必需*: Example value: 20

- `cursor` (string): Example value: 



---


### `get_user_by_username`

Gets a user by username

**端点**: `GET /user`


**参数**:

- `username` (string) *必需*: Example value: MrBeast



---


### `get_user_replies`

Get User Replies By ID  You can get the user(rest_id) query from \

**端点**: `GET /user-replies`


**参数**:

- `user` (string) *必需*: Example value: 2455740283

- `count` (string) *必需*: Example value: 20

- `cursor` (string): Example value: 



---


### `get_users_by_ids`

Get Users By IDs (Rest IDs)

**端点**: `GET /get-users`


**参数**:

- `users` (string) *必需*: Example value: 2455740283,44196397



---


### `get_users_by_ids_v2`

Get Users By IDs V2

**端点**: `GET /get-users-v2`


**参数**:

- `users` (string) *必需*: Example value: 1222790936679206913,133938408,34186021



---


### `get_list_members`

Get List Members by List ID

**端点**: `GET /list-members`


**参数**:

- `listId` (string) *必需*: Example value: 1238730743569772544

- `count` (string): Example value: 20

- `cursor` (string): Example value: 



---


### `get_list__followers`

Get List  Followers by List ID

**端点**: `GET /list-followers`


**参数**:

- `listId` (string) *必需*: Example value: 1238730743569772544

- `count` (string): Example value: 20

- `cursor` (string): Example value: 



---


### `get_trends_by_location`

Get Trends By Location

**端点**: `GET /trends-by-location`


**参数**:

- `woeid` (string) *必需*: This value can be gotten from the Get Available Trends Locations endpoint.

- `exclude` (string): Setting this value equal to hashtags will remove all hashtags from the response list.



---


### `get_available_trends_locations`

Get Available Trends Locations

**端点**: `GET /trends-locations`



---


### `get_post_quotes`

Get Post Quotes By Post ID

**端点**: `GET /quotes`


**参数**:

- `cursor` (string): Example value: 

- `pid` (string) *必需*: Example value: 1552735248026411010

- `count` (string) *必需*: Example value: 40



---


### `get_post_retweets`

Get Post Retweets By Post ID

**端点**: `GET /retweets`


**参数**:

- `cursor` (string): Example value: 

- `pid` (string) *必需*: Example value: 1552735248026411010

- `count` (string) *必需*: Example value: 40



---


### `get_post_comments`

Get Post Comments By Post ID

**端点**: `GET /comments`


**参数**:

- `pid` (string) *必需*: Example value: 1552735248026411010

- `count` (string) *必需*: Example value: 40

- `cursor` (string): Example value: 



---


### `get_tweets_details_by_ids`

Get Tweets Details By Tweet IDs

**端点**: `GET /tweet-by-ids`


**参数**:

- `tweetIds` (string) *必需*: Example value: 1892702078029476328,1885213980739711144,1886671728941924567,1905285543136551299



---


### `get_tweet_details_v2`

Get Tweet Details By Tweet ID

**端点**: `GET /tweet-v2`


**参数**:

- `pid` (string) *必需*: Example value: 1631781099415257088



---


### `job_details`

Get Job Details

**端点**: `GET /job-details`


**参数**:

- `jobId` (string) *必需*: Get this value from \\\\\\\"rest_id\\\\\\\" returned from GET /jobs-search Endpoint



---


### `search_jobs`

Search Jobs

**端点**: `GET /jobs-search`


**参数**:

- `keyword` (string) *必需*: Example value: python

- `count` (string) *必需*: Example value: 20

- `job_location_id` (string): Get this value from GET /jobs-locations-suggest (Search Job Locations).

- `job_location_type` (string): onsite,remote,hybrid. One of them or multiple values with comma as seperator

- `seniority_level` (string): intern,entry_level,junior,mid_level,senior,lead,manager,executive. One of them or multiple values with comma as seperator

- `employment_type` (string): full_time,full_time_contract,part_time,contract_to_hire. One of them or multiple values with comma as seperator

- `cursor` (string): Example value: 



---


### `search_job_locations`

Suggest Job Locations

**端点**: `GET /jobs-locations-suggest`


**参数**:

- `query` (string) *必需*: Example value: CA



---


### `get_user_likes`

Get User Likes By ID  You can get the user(rest_id) query from \

**端点**: `GET /user-likes`


**参数**:

- `user` (string) *必需*: Example value: 2455740283

- `count` (string) *必需*: Example value: 20

- `cursor` (string): Example value: 



---


### `search_twitter_v2`

Search Twitter (Top, Latest, Videos, Photos and People)

**端点**: `GET /search-v2`


**参数**:

- `type` (string) *必需*: Example value: 

- `count` (string) *必需*: Example value: 20

- `cursor` (string): Example value: 

- `query` (string) *必需*: Example value: Mr Beast



---


### `space_details`

Get Space Details By ID

**端点**: `GET /spaces`


**参数**:

- `id` (string) *必需*: Example value: 1djGXrBwYEjxZ



---


### `get_organization_affiliates`

Get  Organization Affiliates By ID  You can get the user(rest_id) query from \

**端点**: `GET /org-affiliates`


**参数**:

- `user` (string) *必需*: Example value: 377228272

- `count` (string) *必需*: Example value: 20

- `cursor` (string): Example value: 



---


### `search_twitter`

Search Twitter (Top, Latest, Videos, Photos and People)

**端点**: `GET /search`


**参数**:

- `type` (string) *必需*: Example value: 

- `count` (string) *必需*: Example value: 20

- `query` (string) *必需*: Example value: Mr Beast

- `cursor` (string): Example value: 



---


### `autocomplete`

Twitter Seach Query Autocomplete

**端点**: `GET /autocomplete`


**参数**:

- `value` (string) *必需*: Example value: MrB



---


### `get_post_likes`

Get Post Likes By Post ID

**端点**: `GET /likes`


**参数**:

- `cursor` (string): Example value: 

- `pid` (string) *必需*: Example value: 1552735248026411010

- `count` (string) *必需*: Example value: 40



---



## 技术栈

- **传输协议**: stdio
- **HTTP 客户端**: httpx

## 开发

此服务器由 [API-to-MCP](https://github.com/BACH-AI-Tools/api-to-mcp) 工具自动生成。

版本: 1.0.0
