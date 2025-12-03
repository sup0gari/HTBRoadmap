## TTYシェルの確立
リバースシェルで獲得したシェルが不安定な場合、TTYシェルを確立することで安定したインタラクティブなシェルが得られる。  
`python3 -c "import pty;pty.spawn('/bin/sh')"`

## ブラウザでドメインの名前解決ができないとき
`echo <ターゲット> <ドメイン> | sudo tee -a /etc/hosts`

## シェルの切り替え
```
sudo su - # rootシェル
sudo -i # rootシェル
```

## 任意のファイルをHTTP経由で配布(python3を使用)
```bash
python3 -m http.server 8000 # 任意のファイルがあるディレクトリで実行
```
