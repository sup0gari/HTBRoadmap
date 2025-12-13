# ldapsearchとは
LDAPサーバーに対して検索クエリを発行し、情報を取得するためのコマンドラインツール。

## コマンド
```bash
ldapsearch -H ldap://<ターゲット> -x -b "dc=<ドメイン>" # 匿名バインド
ldapsearch -H ldap://<ターゲット> -x -b "dc=<ドメイン>" -s sub "*" | grep -i lock # アカウントロックポリシー確認
ldapsearch -H ldap://<ターゲット> -D <ユーザー>@<ドメイン> -b "dc=<ドメイン>" -w '<パスワード>' "*" # 認証ありバインド
```
