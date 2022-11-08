# Gin-Line-MongoDB Demo

Spec :
commit #1 setup project

commit #2 Makefile or a script for local setup and run MongoDB docker (version: 4.4)

commit #3 setup necessary config of LINE, MongoDB
          Line official account message integration (use go line sdk),Create a test line dev official account

commit #4 Create a Go package connect to mongoDB, create a model/DTO to save/query user message to MongoDB

commit #5 Create a Gin API
receive message from line webhook, save the user info and message in MongoDB
(Hint: using ngrok for local test to generate a https endpoint)

commit #6 Create a API send message back to line

commit #7 Create a API query message list of the user from MongoDB

provide a demo video or steps of test (or postman or ...)





### 執行步驟
#### 初始化
* Step1. Build Config
```sh
cp .env.example .env
```

* Step2. Change .env config (LineBot & MongoDB)
```sh
DB_CONNECTION = mongodb
DB_HOST = mongo
DB_PORT = 27017
DB_USERNAME = admin
DB_PASS = admin

LINE_CHANNEL_ID =
LINE_CHANNEL_SECRET =
LINE_CHANNEL_ACCESS =
```

* Step3. Login
  [Line Developers](https://developers.line.biz/en/)



* Step4. Line Webhook Setting
  點擊[Messaging API](https://developers.line.biz/en/services/messaging-api/)
  
  
* Step5. Local Testing (Using Ngrok)

  *example
  `https://{some domain}/messages/receive`

#### 啟動專案
```sh
docker-compose up -d --build
```

### 使用範例
* 連接測試

`curl https://{some domain}`
* 取得官方帳號訊息列表

`[GET] https://{some domain}/user/{Line official account user id}/messages`
* 利用官方帳號推送訊息

`[POST] https://{some domain}/messages/push`
```sh
# Content-Type: application/json
# Body parameters
{
    "UserID": "Line official account user id",
    "Content": "some message you want to push"
}
```
