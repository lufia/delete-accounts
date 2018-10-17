## 公式URL

- [Skype.com](https://skype.com/)

## 削除方法

Web上で削除可能ですが、Skypeだけ削除することはできません。
Microsoftアカウントと同時に削除する対応となります。

1. [アカウントの削除ページ](http://go.microsoft.com/fwlink/?LinkId=523898)を開く
2. あとは[Microsoftアカウントの削除](microsoft.md)と同じ

サポートページに[Skypeでアカウントを削除する方法を教えてください](https://support.skype.com/ja/faq/FA142/skypedeakauntowoxue-chu-surufang-fa-wojiao-etekudasai)という記事があります。

## バックアップ

macOS版の8.x以降は、**~/Library/Application Support/Skype/*(skype-id)*/main.db** に会話ログが記録されています。
これはSQLiteファイルなので、*sqlite* コマンドで読み取ることができます。

```console
$ echo 'select datetime(timestamp,"unixepoch","localtime"), author, from_dispname, body_xml from Messages;' |
> sqlite3 ./main.db -csv
```

7.xまでの会話ログは、8.xのSkypeを起動して、

1. 環境設定を開く
2. メッセージングタブを選択
3. Skype 7.xからチャットの履歴をエクスポート

でエクスポート可能です。

* [skypeの全チャットログを読みやすい形で保存する(mac)](https://qiita.com/dai___chi/items/ea4ff70fca99edabae29)
