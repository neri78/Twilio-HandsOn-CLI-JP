#  手順3: プロジェクトのデプロイとTwilio番号の着信設定
## はじめに
Serverless Toolkitを使うとTwilio RuntimeにWebアプリケーションを簡単にデプロイできます。このハンズオンでは、先ほどの手順で作成したアプリケーションをデプロイし、さらにTwilio番号に着信があった際にそちらを利用する方法を体験します。

## この手順を進めるための前提条件
- Serverless Toolkitでプロジェクトを作成済みであること。

## 3-1. プロジェクトをTwilio Runtimeにデプロイ

ローカルでデプロイ予定のアプリケーションを実行している場合は一旦中断させます。

次のコマンドを実行すると、Twilioプロジェクトにアプリケーションのデプロイを開始します。

```
twilio serverless:deploy
```
デプロイ先の情報や __SID__ が出力されます。

```
Deploying functions & assets to the Twilio Runtime
Account         SKxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
Token           USyf****************************
Service Name    cli-handson
Environment     dev
Root Directory  C:\Users\dikehara\cli-handson
Dependencies
Env Variables
√ Serverless project successfully deployed
Deployment Details
Domain: cli-handson-xxxx-dev.twil.io
Service:
   cli-handson (ZSxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx)
Environment:
   dev (ZExxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx)
Build SID:
   ZBxxxxxxxxxxxxxxxxxxxxxxxxxxx
View Live Logs:
   https://www.twilio.com/console/assets/api/ZSxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx/environment/ZExxxxxxxxxxxxxxxxxxxxxxxxxxx
ddc140
Functions:
   https://cli-handson-xxxx-dev.twil.io/never-gonna-give-you-up
Assets:
```
出力内容にエラーがないことを確認し、`Functions:`に表示されているURLを控えてください。

## 3-2. 着信応答の設定

ここではTwilio番号に着信があった際のTwiMLのURLとして`--voice-url`に先ほどのURLを指定します。
次のコマンドをご自身のTwilio番号に変更し設定してください。
```
twilio phone-numbers:update +12xxxxxxxxx --voice-url https://cli-handson-xxxx-dev.twil.io/never-gonna-give-you-up --voice-method GET
```

このTwilio番号に電話をかけ、TwiMLに設定されている音楽が再生されることを確認してください。

ここまででハンズオンとしては一旦終了となります。時間が余るようであれば、次のセクションに挑戦してみてください。

なお、今回デプロイしたアプリケーションは __公開__ 状態となっているため、誰もがアクセスできます。Twilio Functionsは実行ごとに課金されるため、不要になった段階で、[コンソール](https://jp.twilio.com/console/functions/overview/services)から、あるいは下記の手順で削除してください。

1. 現在デプロイしているサービスを確認し、`SID`を控える
```
twilio serverless:list

実行結果
Account      SK******************************
Token        Yd******************************
Service      ZS******************************
Environment  dev

Services:

cli-handson
│ SID:      ZS******************************
│ Created:  Oct 08 2020 14:32:00 GMT+0900
│ Updated:  Oct 08 2020 14:32:00 GMT+0900
```
2. `cli-handson`の`SID`を指定し、サービスを削除する。
```
twilio api:serverless:v1:services:remove --sid ZS******************************
```

同様に不要な電話番号を[コンソール](https://jp.twilio.com/console/phone-numbers/incoming)、またはCLIを用いて削除できます。CLIのコマンドについては一部のみ記載します。これまで学習してきた内容を元に調べてみましょう。

```
twilio api:core:incoming-phone-numbers
```

## 3-3.（挑戦）Functionの実装内容を変更し、再度デプロイ

[TwiML - Say](https://www.twilio.com/docs/voice/twiml/say)を参考に、音楽の再生前に日本語で `今日のハンズオン、お疲れさまでした。こちらの音楽をお聞きください`というメッセージを再生してみましょう。  
__ヒント: `never-gonna-give-you-up.js`を変更し再度デプロイします。__

## 3-4.（挑戦）TwilioQuestをプレイ

Twilio CLIだけではなく、他のTwilio製品を楽しみながら学びたいという方は、下記の記事を参考にRPGゲームを模したチュートリアル `TwilioQuest`のプレイに挑戦してみてください。

- [Game + Tutorial = TwilioQuest3のはじめかた](https://www.twilio.com/blog/game-tutorial-twilioquest)


- 関連リソース
  - [Deploying with the Serverless Toolkit](https://jp.twilio.com/docs/labs/serverless-toolkit/deploying)
  - [Twilio CLI Quickstart](https://jp.twilio.com/docs/twilio-cli/quickstart)
