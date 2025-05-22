# HTTP Last-Modified テスト

Vite+React+Vercelで構築したHTTPヘッダーテスト用サイトです。主に`Last-Modified`ヘッダーと`304 Not Modified`レスポンスの動作確認を目的としています。

## 検証方法

### curlでの確認

```bash
# 初回アクセス
curl -I https://lastmodified-attr-on-header2.vercel.app

# 再アクセス（If-Modified-Sinceを指定）
curl -I -H "If-Modified-Since: <前回のLast-Modified値>" https://lastmodified-attr-on-header2.vercel.app/
```

### ブラウザでの確認

1. Chrome DevToolsを開く（F12）
2. Networkタブを選択
3. ページをリロード
4. documentタイプのリクエストで`304 Not Modified`を確認

## 動作の流れ

1. 初回アクセス: `200 OK` + `Last-Modified`ヘッダー
2. 再アクセス: `304 Not Modified`（変更がない場合）

## 起動方法

```bash
npm install
npm run dev
```

# Zenn 記事
piyopiyo
