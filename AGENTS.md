# なくしもの探知機

Flet Web アプリ（Pyodide / GitHub Pages デプロイ）

## 重要: 命令形API必須
宣言的API (`@ft.component` + `page.render()`) は Pyodide で動かない。
必ず命令形API (`def main(page):` + `page.add()` + `page.update()`) を使う。

## 構成
- `main.py` — 全実装（命令形API, NavigationBar パターン）
- `.github/workflows/deploy.yml` — GitHub Actions 自動デプロイ
- `requirements.txt`: `flet>=0.85.0`
- storage key: `lost_items_v4`（localStorage）

## 使用Flet機能
- `ft.NavigationBar` + 動的view切替 (下部ナビ)
- `ft.AppBar` (タイトルバー + Export/Import)
- `ft.Ref[ft.TextField]()` (リファレンスによる制御)
- `ft.Theme` + `ft.ColorScheme` (色テーマ)
- `ft.ProgressBar` (分析ローディング)
- `ft.SafeArea` (モバイルセーフエリア対応)
- `ft.Card` + `ft.ListTile` + `elevation` (カード表示)
- `ft.Dismissible` (スワイプ削除)
- `ft.AlertDialog` + `ft.SnackBar` (ダイアログ)
- `js.window.localStorage`（データ永続化、フォールバック: page.client_storage）
- `ft.Colors`, `ft.Icons`, `ft.FontWeight` など

## 最終状態
- 白画面バグ修正済み
- データ永続化: localStorage直接保存
- 下部NavigationBar + 動的view切替
- カード elevation + Dismissible スワイプ削除
- **次回: プッシュ後 https://shin488.github.io/lost-items/ を確認**
