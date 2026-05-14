# JadeWM

smallvil (Smithay) をベースにした、シンプルなタイル型 Wayland コンポジタです。

## 実装方針

- サーバーサイドデコレーションは提供しません（デコレーションなしWM）。
- ウィンドウはタイル配置のみです。
- move/resize 要求は無効化しています。

## タイルレイアウト

- 1枚目: マスター領域（画面幅の 60%）
- 2枚目以降: 右側スタック領域を縦分割

## 起動

```bash
cargo run
```

別端末でアプリをこのコンポジタに接続する場合:

```bash
WAYLAND_DISPLAY=<表示されたソケット名> <アプリ>
```

## Tailwind CSS 装飾（任意）

このWM本体はデコレーションを描画しません。
Tailwindベース装飾を使いたい場合は、Waylandクライアント側で装飾を描画してください。
サンプルは [ui/decorations.html](ui/decorations.html) にあります。
