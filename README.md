# WP ENV

## 概要
- `wp-env`を使用して、WordPressのローカル環境を構築

## 事前準備
- Dockerを使える環境
- Node(npm)を使える環境

## ローカル環境作成
- 事前設定
  - .wp-env.json
    - core
      - WordPressのバージョン設定
    - phpVersion
      - PHPのバージョンを設定
    - plugins
      - インストールしておくプラグインを設定
    - themes
      - インストールしておくテーマを設定
    - port
      - ローカルでみるためのポートを設定
      - env>tests>port は設定が必要(テスト環境用)
    - mappings
      - ローカルとコンテナ側でのディレクトリの紐付け

- 必要ログイン情報
  - ユーザー名： admin
  - パスワード： password

- パッケージのインストール
```
$ npm ci
```

- ローカル環境実行
  - `--update`：更新した状態で起動することが可能
```
$ npm run wp-env start
```

- ローカル環境停止
```
npm run wp-env stop
```

- ローカル環境削除
```
npm run wp-env destroy
```

- DBのエクスポート
```
npm run wp-env run cli wp db export sql/db-data.sql
```

- DBのインポート
```
npm run wp-env run cli wp db import sql/db-data.sql
```

- DB内の置換
```
npm run wp-env run cli wp search-replace 'http://localhost:8080' 'http://localhost:8081'
```

## 参考文献
- [@wordpress/env：WordPress.org 日本語](https://ja.wordpress.org/team/handbook/block-editor/reference-guides/packages/packages-env/)
- [WordPress制作環境の過去と現在、そして未来はどうなる？wp-envの使い方を紹介](https://liginc.co.jp/612383)
