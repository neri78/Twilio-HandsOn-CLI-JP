#  手順1: Twilio CLIをインストール
## はじめに
この手順では、Twilio CLIを開発マシンにインストールする方法を学びます。Twilioアカウントを作成します。既にCLIをインストールしている場合は、[手順2: TwilioアカウントをCLIに登録]()へ進んでください。

## この手順を進めるための前提条件
Twilio CLIをWindows/Macにインストールする場合は、次の環境が必要になります。

- インターネット環境への接続
- [Node.js (10.12以降)](https://nodejs.org/ja/)
- Twilioアカウント（[作成方法](https://www.twilio.com/blog/how-to-create-twilio-account-jp)）

## 1-1. Twilio CLIのインストール

CLIをインストールするため、シェル（ターミナル）、またはコマンドプロンプトを開き次のコマンドを実行します。

```bash
npm install twilio-cli -g
```

CLIと依存パッケージがインストールされます。完了後、次のコマンドを実行し動作を確認します。

----
npmの利用を推奨していますが、Macの場合は、[Homebrew](https://brew.sh/)も選択できます。Linuxの場合と併せて下記のドキュメントをご覧ください。  
[Twilio CLI Quickstart](https://jp.twilio.com/docs/twilio-cli/quickstart)

----


```
twilio
```
実行結果（Mac OS X、Node.js V12.18.2の場合）
```
$ twilio
unleash the power of Twilio from your command prompt

VERSION
  twilio-cli/2.13.0 darwin-x64 node-v12.18.2

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
```

## 次の手順
- [手順2: TwilioアカウントをCLIに登録](02-Create-Twilio-Profile.md)
