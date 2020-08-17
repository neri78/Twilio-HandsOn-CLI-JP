#  手順3: CLIを使ったステータスの確認とSMSの発信
## はじめに
Twilio CLIには現在アクティブなプロファイルにひもづくプロジェクトのアクティビティをモニタリングできる便利な機能を提供しています。この機能を利用し、デバッグ時にTwilioに関するアクティビティをリアルタイムで確認できます。  
また、音声機能だけではなく、SMS発信機能についてもこのハンズオンで体験します。

## この手順を進めるための前提条件
- Twilio CLIがすでにインストールされており、音声通話が可能な電話番号を購入済みであること。

## 3-1. watchを起動

次のコマンドを実行すると、中断されるまでTwilioプロジェクトのアクティビティを出力し続けます。

```
twilio watch
```

コマンドが見つからない等のエラーが表示された場合は、次のコマンドで`watchプラグイン`をインストールした後に再度試してください。

```
twilio plugins:install @twilio-labs/plugin-watch
```

この`watch`を実行させたまま、購入済みのTwilio番号に電話をかける、あるいは別のシェル（ターミナル）またはコマンドプロンプトを開き、電話の発信を行うと、下記のようにログが出力されることを確認してください。
```
And now my watch begins. It shall not end until CTRL-C (SIGINT).
Date                 Type         Code         Text
2020-08-17 14:21:21  call[in]     ringing      FROM: +81xxxxxxxxxx, TO: +1xxxxxxxxxx
2020-08-17 14:21:21  call[in]     in-progress  FROM: +81xxxxxxxxxx, TO: +1xxxxxxxxxx
2020-08-17 14:21:42  call[in]     completed    FROM: +81xxxxxxxxxx, TO: +1xxxxxxxxxx
```

## 3-2. SMSを送信

SMSの送信も試してみましょう。次のコマンドを`--from`をご自身のTwilio番号、`--to`を検証済みの電話番号に変更し、SMSが届くことを確認しましょう。

```
twilio api:core:messages:create --from +1xxxxxxxxxx --to +81xxxxxxxxxx --body はろー
```

`watch`を別に起動している場合はこちらのアクティビティが出力していることを確認できます。

## 関連リソース

- [Twilio CLI Quickstart](https://www.twilio.com/docs/twilio-cli/quickstart)



## 次の手順
[ハンズオン: Twilio CLIを使ったサービスの利用](../03-Use-Serverless-Toolkit/03-00-Overview.md)