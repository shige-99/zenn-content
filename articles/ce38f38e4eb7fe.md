---
title: "Customizing Colors - Tailwind CSS"
emoji: "🎨"
type: "tech"
topics:
  - "tailwindcss"
published: true
published_at: "2024-06-17 23:35"
---

## Tailwind CSSとは

Tailwind CSSは、クラス名に特定のスタイル（例えば、margin、padding、colorsなど）を直接反映させるユーティリティファーストのCSSフレームワークです。
また、ユーティリティファーストの設計手法を採用している事で、簡潔かつ直感的にスタイルを適用できます。

## フレームワークの特徴

Tailwind CSSはフレームワークということもあり、デフォルトのカラーパレットには制限があります。そのため、使用したいカラーを指定する際は、拡張設定を行う必要があります。

## カラーの指定方法

### 指定先ファイル

- tailwind.config.js

デフォルトの `tailwind.config.js` は以下のようになります。

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

これを拡張設定します。

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ['./src/**/*.{html,js,svelte,ts}'],
  theme: {
    extend: {
      colors: {    // 追加
          'dark': '#424769',    // 好きな色を指定
          'light': '#676f9d',
          'font': '#ffffff',
          'button': '#f9b17a'
        }
    },
  },
  plugins: [],
}
```

`colors: {...}` 内に `'クラス名': 'カラーコード'` を記入することで、カスタムカラーを追加できます。

## カスタムカラーの使用方法

カスタムカラーをTailwind CSSの記述方法に従って使用します。

```html
<div class="bg-light">
  <h1 class="text-font">Hi, there👋🏻</h1>
  <p class="text-font">
    Shige is a software developer based in Tokyo.
  </p>
</div>
```

## まとめ
色を管理する際に、予め`tailwind.config.js` でセットしておくと便利です。他に色の管理方法があれば、是非教えて下さい。

## 参考文献

https://tailwindcss.com/docs/customizing-colors#extending-the-defaults
https://fwywd.com/tech/tailwindcss-color-palette