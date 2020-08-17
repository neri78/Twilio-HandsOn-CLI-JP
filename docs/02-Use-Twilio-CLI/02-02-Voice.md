#  手順2: CLIを使った電話の着信設定と発信
## はじめに
この手順では、購入した電話番号を使った音声通話の着信の応答設定と発信をCLIで設定・実行します。

## この手順を進めるための前提条件
- Twilio CLIがすでにインストールされており、音声通話が可能な電話番号を購入済みであること。

## 2-1. 購入済みの電話番号を確認

次のコマンドで購入済みの電話番号を確認します。

```
twilio phone-numbers:list
```
番号購入時にも表示された`SID, Phone Number, Friendly Name`が表示されます。この中で、__E.164フォーマット__ で表示されている`Phone Number`を控えておきます。
```
SID                                 Phone Number  Friendly Name
PNxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  +12xxxxxxxxx  (2xx) xxx-xxxx
```

## 2-2. 着信応答の設定

Twilioは着信応答時に[TwiML](https://jp.twilio.com/docs/voice/twiml)と呼ばれているマークアップ言語で応答メッセージを設定できます。この場合は、`--voice-url`で __TwiML__ がホスティングされているURLを指定できます。  
次のコマンドをご自身のTwilio番号に変更し設定してください。
```
twilio phone-numbers:update +12xxxxxxxxx --voice-url https://demo.twilio.com/
welcome/voice/ja --voic
e-method GET
```
実行結果が表示されます。
```
SID                                 Result   Voice URL                               Voice Method
PNxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  Success  https://demo.twilio.com/
welcome/voice/ja  GET
```
このTwilio番号に電話をかけてみてください。  
トライアル版の場合は最初にトライアル版を利用中であるというメッセージが再生され、何かキーを押すことで指定したメッセージを再生できます。日本語のメッセージが再生されることを確認しましょう。

## 2-3. 検証済み番号にTwilio番号から発信

Twilio CLIを用いて電話を発信する場合は、`api:core:calls:create`コマンドを使用します。その際、`--from`に先ほど控えたTwilio番号を、`--to`に発信先番号を指定します。接続後に再生されるメッセージは[TwiML](https://jp.twilio.com/docs/voice/twiml)で定義する必要があり、そのTwiMLがホストされている場所を`--url`で指定します。  
下記のコマンドをご自身の番号に変更し、実行してください。
```
twilio api:core:calls:create --from +12xxxxxxxx --to +81xxxxxxxxxx --url https://demo.twilio.com/docs/voice.xml
welcome/voice/ja
```
コマンドや番号が正しければ、キューに追加された状態が表示されます。
```
SID                                 From          To             Status  Start Time
CAxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  +12xxxxxxxxx  +819xxxxxxxxx  queued  null
```
いかがでしょう、ご自身の番号に着信はありましたか？何が再生されたでしょうか？ぜひ、確認してみてください。

さて、トライアル版の場合は、検証済みの番号にのみ発信が可能であるという点に注意が必要です。検証済みでない番号に発信を行うと、下記のようなエラーメッセージが表示されます。

```
» Error code 21219 from Twilio: The number +818xxxxxxxxx is unverified. Trial accounts may only make calls to verified
numbers.. See https://www.twilio.com/docs/errors/21219 for more info.
```

## 関連リソース

- [TwiML](https://jp.twilio.com/docs/voice/twiml)
- [Twilio CLI Quickstart](https://www.twilio.com/docs/twilio-cli/quickstart)



## 次の手順
[手順3: CLIを使ったステータスの確認とSMSの発信](./02-03-Watch-SMS.md)