# Gin-Line-MongoDB Demo


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
  `https://{domain}/messages/receive`

#### 啟動專案
```sh
docker-compose up -d --build
```

### How To Use
* 連接測試

`curl https://{domain}`
* 取得官方帳號訊息列表

`[GET] https://{domain}/user/{Line official account user id}/messages`
* 利用官方帳號推送訊息

`[POST] https://{domain}/messages/push`
```sh
# Content-Type: application/json
# Body parameters
{
    "UserID": "Line official account user id",
    "Content": "some message you want to push"
}
```
