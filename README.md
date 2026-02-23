# reflex-math

加法分解構造の反射トレーニング — 足し算・引き算を反射的に解くためのトレーニングアプリ

## 概要

1〜9の数の加法分解（a + b = c）を6つの出題形式で繰り返し練習し、反射的に解答できるようにするアプリです。

### 特徴
- **適応的出題**: 苦手な組み合わせが自動的に多く出題される
- **二峰分析**: 反射クラスタと思考クラスタを自動識別し、個人のベースラインを算出
- **苦手インデックス**: 各組み合わせの習熟度を0〜10で数値化
- **6つの出題形式**: `a+b=?`, `a+?=c`, `?+b=c`, `c-a=?`, `c-?=a`, `?-b=a`
- **音声入力対応**: Web Speech API による日本語音声認識

## 使い方

### ブラウザで開く
`index.html` をブラウザで開くだけで動作します。

### GitHub Pages で公開
1. このリポジトリをfork or clone
2. Settings → Pages → Source: main / root → Save
3. `https://あなた.github.io/reflex-math/` でアクセス

### Android アプリ化（TWA）
```bash
npm i -g @nickersoft/bubblewrap  # ← 正しくは:
npm i -g @bubblewrap/cli
bubblewrap init --manifest="https://あなた.github.io/reflex-math/manifest.json"
bubblewrap build
```

## ファイル構成
```
reflex-math/
├── index.html              # メインアプリ（単一ファイル HTML/CSS/JS）
├── manifest.json           # PWA Web App Manifest
├── sw.js                   # Service Worker（オフライン対応）
├── icon-192.png            # アプリアイコン 192x192
├── icon-512.png            # アプリアイコン 512x512
├── icon-maskable-192.png   # マスカブルアイコン 192x192
├── icon-maskable-512.png   # マスカブルアイコン 512x512
└── .well-known/
    └── assetlinks.json     # Digital Asset Links（TWA用、要編集）
```

## データ保存
ブラウザの `localStorage` に保存されます（`keisan_master_v2` キー）。デバイス・ブラウザごとに独立です。

## ライセンス
MIT
