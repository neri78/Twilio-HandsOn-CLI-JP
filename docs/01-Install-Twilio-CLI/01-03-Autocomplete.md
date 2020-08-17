#  手順3: CLIにオートコンプリート機能を追加（bashまたはzsh）
## はじめに
Twilio CLIは公開されているAPIの機能を数多く利用することができる反面、コマンドの入力文字数が膨大になりがちです。この短所を解決するために`Tab`キーで入力候補を表示できるオートコンプリート機能を用意しています。  
この手順では、インストールしたTwilio CLIのコマンド入力を補助するオートコンプリート機能をインストールします。この機能は `bash`または、`zsh`のみに現在対応しているため、対応するシェルを使用していない場合、あるいはすでにこの機能をインストール済みの場合は、[ハンズオン: Twilio CLIを使ったサービスの利用]()へ進んでください。

## この手順を進めるための前提条件
- Twilio CLIがすでにインストールされていること
- bashまたはzshシェルを利用していること

## 3-1. オートコンプリート機能をインストール

利用しているシェルごとに次のコマンドを実行し、オートコンプリート機能をインストールします。

- __bash__ を利用している場合
```
twilio autocomplete bash
```

インストール後に表示されるメッセージに従い、環境変数を追加し、シェルを再起動してください。
 
```
$ twilio autocomplete bash
Building the autocomplete cache... done

Setup Instructions for TWILIO CLI Autocomplete ---

1) Add the autocomplete env var to your bash profile and source it
$ printf "$(twilio autocomplete:script bash)" >> ~/.bashrc; source ~/.bashrc

NOTE: If your terminal starts as a login shell you may need to print the init script into ~/.bash_profile or ~/.profile.

2) Test it out, e.g.:
$ twilio <TAB><TAB>                 # Command completion
$ twilio command --<TAB><TAB>       # Flag completion

Enjoy!
```

- __zsh__ を利用している場合
```
twilio autocomplete zsh
```
インストール後に表示されるメッセージに従い、環境変数を追加し、シェルを再起動してください。
 
```
% twilio autocomplete zsh
Building the autocomplete cache... done

Setup Instructions for TWILIO CLI Autocomplete ---

1) Add the autocomplete env var to your zsh profile and source it
$ printf "$(twilio autocomplete:script zsh)" >> ~/.zshrc; source ~/.zshrc

NOTE: After sourcing, you can run `$ compaudit -D` to ensure no permissions conflicts are present

2) Test it out, e.g.:
$ twilio <TAB>                 # Command completion
$ twilio command --<TAB>       # Flag completion

Enjoy!

```

## 3-2. オートコンプリート機能を確認

シェルを再起動後に次の文字列を入力し、`Tab`キーを押して、オートコンプリート機能が動作していることを確認します。

```
twilio pro <Tabキーを押下>
```
この場合は `profiles`コマンドが補完され、再度`Tab`キーを押すとオプションが表示されます。

```
$ twilio profiles:
create  list    remove  use     
```

`profiles:list`コマンドを実行し、先ほど登録したプロファイルが表示されることを確認してください。


## 関連リソース

- [Twilio CLI Quickstart](https://www.twilio.com/docs/twilio-cli/quickstart)



## 次の手順
[ハンズオン: Twilio CLIを使ったサービスの利用](../02-Use-Twilio-CLI/02-00-Overview.md)