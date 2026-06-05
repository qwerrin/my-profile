# Portfolio

個人ポートフォリオサイト（深海テーマ）。GitHub Pages で静的ホスティングする前提の、単一HTML構成。

公開URL: https://qwerrin.github.io/my-profile/

---

## ローカル確認方法

ビルド不要。`index.html` をブラウザで直接開くだけで確認できます。

フォント読み込みなど `file://` で挙動が変わる場合は、簡易サーバーを使ってください：

```bash
# Python 3 がある場合
python -m http.server 8080
# → http://localhost:8080 で確認
```

---

## GitHub Pages デプロイ手順

1. GitHub に公開リポジトリを作る（例：`portfolio`）
2. このフォルダの中身を push する
3. リポジトリの **Settings → Pages → Source** を「Deploy from a branch」、Branch を `main` / `(root)` に設定
4. 数分後 `https://<ユーザー名>.github.io/<リポジトリ名>/` で公開される

`.nojekyll` が置いてあるので Jekyll 処理は自動的に無効化されます。

---

## 後で差し替える箇所

| 箇所 | 内容 |
|------|------|
| ヒーロー・ナビロゴ・フッター | `【後で差し替え：ハンドル名（例：メンダコ）】` → 実際のハンドル名 |
| `assets/mendako.svg` | 暫定SVGプレースホルダ → 本物のメンダコアイコン（SVG or PNG）に差し替え |
| Works カード1 のリンク | `【後で差し替え：営業ページの公開URL】` → 実際のURL |
| Works カード2 | 居酒屋デモボット完成後にタイトル・概要・技術・URLを更新 |
| Contact — X | `【後で差し替え：XのURL】` → 実際のURL |
| Contact — note | `【後で差し替え：noteのURL】` → 実際のURL |
| Contact — お問い合わせ | `【後で差し替え：問い合わせ手段（フォームURL等）】` → 実際のURL |
| Skills の注記 | `【一部は習得中。後で調整】` → 確定後に削除または書き換え |
| OGP（任意） | `assets/og-image.png` と `<meta property="og:*">` タグを追加 |

---

## ファイル構成

```
/
├── index.html        … 本体（HTML / CSS / JS 全部入り）
├── assets/
│   └── mendako.svg   … メンダコアイコン（暫定SVGプレースホルダ）
├── .nojekyll         … GitHub Pages の Jekyll 処理を無効化
└── README.md         … このファイル
```

---

## 技術構成

- 素の HTML / CSS / JavaScript（外部ライブラリ・CDN・ビルドツールなし）
- フォントのみ Google Fonts（Zen Kaku Gothic New）を `<link>` で読み込み
- アニメーション：CSS `@keyframes` + `IntersectionObserver`（Vanilla JS）
- `prefers-reduced-motion` 対応済み
