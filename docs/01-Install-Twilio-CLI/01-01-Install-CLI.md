#  手順1: Twilio CLIをインストール
## はじめに
この手順では、Twilio CLIを開発マシンにインストールする方法を学びます。Twilioアカウントを作成します。既にCLIをインストールしている場合は、[手順2: TwilioアカウントをCLIに登録]()へ進んでください。

## この手順を進めるための前提条件
Twilio CLIをWindows/Macにインストールする場合は、次の環境が必要になります。

- インターネット環境への接続
- [Node.js (10.12以降)](https://nodejs.org/ja/)
- Twilioアカウント（[作成方法](https://www.twilio.com/blog/how-to-create-twilio-account-jp)）

Macの場合は、[Homebrew](https://brew.sh/)を用いてインストールすることも可能です。Linuxの場合と併せて下記のドキュメントをご覧ください。
[Twilio CLI Quickstart](https://www.twilio.com/docs/twilio-cli/quickstart)

## 1-1. Twilio CLIのインストール

CLIをインストールするため、シェル（ターミナル）、またはコマンドプロンプトを開き次のコマンドを実行します。

```bash
npm install twilio-cli -g
```

CLIと依存パッケージがインストールされます。完了後、次のコマンドを実行し動作を確認します。

```
twilio
```
実行結果（Mac OS X、Node V12.18.2の場合）
```
$ twilio
unleash the power of Twilio from your command prompt

VERSION
  twilio-cli/2.7.0 darwin-x64 node-v12.18.2

USAGE
  $ twilio [COMMAND]

COMMANDS
  api            advanced access to all of the Twilio APIs
  autocomplete   display autocomplete installation instructions
  debugger       Show a list of log events generated for the account
  email          sends emails to single or multiple recipients using Twilio
                 SendGrid
  feedback       provide feedback to the CLI team
  help           display help for twilio
  login          create a new profile to store Twilio Account credentials and
                 configuration
  phone-numbers  manage Twilio phone numbers
  plugins        list available plugins for installation
  profiles       manage credentials for Twilio profiles
  serverless     locally develop, debug and deploy to Twilio Serverless
  watch          Keep an eye on incoming alerts, messages, and calls. Polls
                 every 1 second.
```

## 関連リソース

- [Twilio CLI Quickstart](https://www.twilio.com/docs/twilio-cli/quickstart)


## 次の手順
[手順2: TwilioアカウントをCLIに登録](./01-02-Create-Twilio-Profile.md)
