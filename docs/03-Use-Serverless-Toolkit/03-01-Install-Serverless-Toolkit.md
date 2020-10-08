#  手順1: Serverless Toolkitのインストール
## はじめに
この手順では、Twilio Serverless Toolkitのインストール方法を学びます。

Serverless Toolkitはサーバーレス実行環境を提供する[Twilio Runtime](https://www.twilio.com/runtime)に関連する機能をCLIで使いやすくするために開発されました。このプラグインのソースコードはこちらで公開されています。  

[GitHub - twilio-labs/serverless-toolkit](https://github.com/twilio-labs/serverless-toolkit)

## この手順を進めるための前提条件
- Twilio CLIがインストールされていること。
- Node.jsのバージョンが `v10.17.0`以上であること。


## 3-1. Serverless Toolkitをインストール

次のコマンドを実行し、Serverless Toolkitをインストールします。
```
twilio plugins:install @twilio-labs/plugin-serverless
```
Node.jsのバージョンが `v10.17.0`よりも小さい場合はインストール中にエラーメッセージが表示されるため、[Node.jsサイト](https://nodejs.org/ja/)から条件を満たすインストーラーをダウンロードし、アップデートを行うか、利用しているNode管理ツールを用いて使用するNodeバージョンを変更してください。

インストールが完了状態で、次のコマンドを実行します。

```
twilio serverless
```

利用可能なコマンド一覧が表示されていればServerless Toolkitのインストールは成功です。

```
locally develop, debug and deploy to Twilio Serverless
USAGE
  $ twilio serverless:COMMAND
COMMANDS
  serverless:deploy          deploys your local serverless project
  serverless:init            creates a new Twilio Serverless project
  serverless:list            lists services, projects and similar related to your project
  serverless:list-templates  Lists the available Twilio Function templates
  serverless:logs            Print logs from your Twilio Serverless project
  serverless:new             bootstraps a new function in your local project
  serverless:promote         moves an active deployment from one environment to another
  serverless:start           starts a local development environment
```

## 関連リソース

- [Twilio CLI Plugins](https://www.twilio.com/docs/twilio-cli/plugins#install-a-plugin)
- [Install the Twilio Serverless Toolkit](https://www.twilio.com/docs/labs/serverless-toolkit/getting-started#install-the-twilio-serverless-toolkit)
- [Serverless Toolkit](https://www.twilio.com/docs/labs/serverless-toolkit)
- [Twilio CLI Quickstart](https://www.twilio.com/docs/twilio-cli/quickstart)


## 次の手順
[手順2: プロジェクトの作成](./03-02-Create-a-Project.md)
