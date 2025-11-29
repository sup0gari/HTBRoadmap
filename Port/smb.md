# SMBとは
NetBIOSを介さずに、TCP/IP上でファイル共有を行うプロトコル。
SMB 1.0のことをCIFSと呼ぶこともある。

## ポート
445

## 接続方法（smbclientを使用）
```bash
smbclient //<ターゲット>/<共有フォルダ> -N # 匿名接続
smbclient //<ターゲット>/<共有フォルダ> -U <ユーザー名> # ユーザーを指定して接続
smbclient -k //<ターゲット>/<共有フォルダ> # Kerberos認証で接続f
```

## コマンド（smbclientを使用）
```bash
get <ファイル名> # ファイルをダウンロード
prompt OFF # 警告などの確認メッセージをオフにする
recurse ON # ダウンロードする時などで再帰をオンにする
mget * # すべてのファイルをダウンロード
```

## その他
末尾に$が付いているフォルダ(ADMIN$, C$, IPC$など)は、管理共有 (Administrative Shares)または隠し共有 (Hidden Shares)と呼ばれ、認証やアクセス方法が通常フォルダと異なる。
