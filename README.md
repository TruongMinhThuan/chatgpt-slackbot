# ChatGPT Slackbot
**このChatGPT Slackbotは現状ChatGPT APIを使えておらずGPT-3で動作しています！**

Slackを通じて会話人工知能のGPT-3を利用するためのBOT。
ChatGPTのAPIはまだ解放されていないので、代わりにOpenAI APIのGPT-3のAPIを利用。
ChatGPTのAPIがリリースされ次第ChatGPTのAPIに切り替える予定。

環境構築にはOpenAIのAPIトークン及びSlackのBoltのアプリケーショントークンが必要。

## ボットの使い方
- AIとの会話: !gpt \[会話内容\]
- 使い方を表示: !gpt-help

セッションの概念はないが、API側には不正行為検出のためにSlack上のユーザーIDを渡している。

## 環境構築
### OpenAIのAPI Token(SECRET KEY)とOrganazation IDを取得。
[OpenAI API Keys](https://beta.openai.com/account/api-keys)にアクセスしてアカウント作成の後、SECRET KEYとOrganization IDを取得。

### Slack Botのトークンの用意
[Bolt 入門ガイド](https://slack.dev/bolt-python/ja-jp/tutorial/getting-started)に準拠。

- SLACK_BOT_TOKEN
- SLACK_APP_TOKEN

を取得しておく。

#### SLACK_BOT_TOKENで要求するスコープ

- chat:write 

#### Event SubscriptionsのSubscribe to Bot Events で要求するスコープ

- message.channels
- message.groups
- message.im
- message.mpim

### インストール方法
Python3.9.6以上で動作を確認済み。

.env ファイルを実行フォルダ内に作成して、自分のクレデンシャル情報を記述

```
ORGANAZTION_ID=org-xxxxxxxxxxxxxxxxx
OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxxx
SLACK_BOT_TOKEN=xoxb-9999999
SLACK_APP_TOKEN=xapp-9999999-9999999
```

あとは以下を実行してイメージをビルド&実行。

```
docker compose up -d --build
```

以上で起動。

```
docker compose down
```

で停止。

```
docker compose logs
```
でログ確認。

## LICNESE
MIT
