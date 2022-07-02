# 概要
上村健輔くんからの仕事依頼。

# 要件
Slackの特定チャンネルに時間を入力すると、その時間にリマインド（メンション）する。

# フロー
1. Slackに個人アカウントでメッセージを入力
2. OutgoingWebhookにてGoogleスプレッドシートに書き込み
3. GASで１分間に1回、スプレッドシートをスクレイピングする。
4. スクレイピングして合致する時間がある場合は、IncomingWebhookにてSlackにメンションを飛ばす。

# GAS
作るべきfunctionまとめ
- OutgoingWebhook受け取り用(予約関数：doPost)
- スプレッドシートのをスクレイピング
- IncomingWebhookを叩く

トリガー
- 1分間に1回スクレイピング関数を実行

# 設計図

# Memo
## 検証環境
### Slack
ワークスペース：40th_18NSJ
チャンネル名：4-1_dev

### Slackインテグレーション
**OutGoingWebhook**<br>
**InComingWebhook**

### GoogleSpreadSheet
[kensuke](https://docs.google.com/spreadsheets/d/1R6pxMaaj7-Dya4TwmqfPEispE0lemsmKuvL-ynEOBlg/edit#gid=0)

### GoogleAppScript
hoge

# Remarks
## GoogleAppScriptの種類
**コンテナバインド型**
- スプレッドシートやフォームに紐づいている
**スタンドアロン型**
- 独立して存在しており、他と依存関係がない