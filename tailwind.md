### Tailwind　とは

Bootstrapのような既にスタイルが定義されたクラス名を利用してDOMのスタイリングを簡単にできるフレームワーク

Bootstrapはコンポーネントのスタイリングも用意している

    例: ボタンを作成したい場合 Bootstrap では .btn-primary .btn-secondary などそれ一つのクラスでボタンのスタイリングができるクラスを用意している

Tailwind ではそのようなコンポーネントレベルのクラスではなく、utility class と呼ばれる定義済みの基本的なスタイリングを利用する

    例: 色やフォントの大きさ、パディングの設定などを組み合わせてボタンを自分好みにスタイリングしていく

上記の意味において Tailwind は low level CSS framework と呼ばれている

---

### Tailwindのみでの利用方法

まずはインストール  
- 以下の2つの方法がある

    1. CDNから取得する方法

    2. npm や yarn からインストールし、プロジェクトに含める方法
        - 開発環境のみで利用するで、 install -D でインストールする

        ```bash
        npm install -D tailwindcss
        ```

<br>

インストール後に Tailwind の設定ファイルを作成する

1. コマンドから作成する 

    ```bash
    npx tailwindcss init
    ```

2. 自分で作成する
    - tailwind.config.js を作成する

<br>

設定ファイル作成後は、cssファイルを作成し、Tailwindを利用するディレクティブを追加する

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

<br>

コマンドで tailwind から css をビルドする

```bash
npx tailwindcss-cli@latest build (-i) <ビルド対象> -o <出力先>
```

---

### なぜ -D　でインストールするのか?

Tailwind はビルド時に実際に利用されているクラスのみをCSSファイルに別途出力し、参照側はそっちのファイルを見るようになるから

---

### Tailwind を　CSS プリプロセッサの plugin として利用する方法

PostCSS の plugin として利用することができる
\*Next.js ではこちらの方法で利用する

create-next-app で Tailwind を利用するを選択した場合、 postcss, tailwindcss はデフォルトでインストールされている状態になる

後は必要に応じて autoprefixer をインストールする
- tailwind はビルド時に ベンダープレフィックスを付けないため

#### autoprefixer　のインストール & 設定

1. インストールする

```bash
npm install -D autoprefixer
```

<br>

2. postcss.config.js に autopefixer を postcss のプラグインとして利用するよう追加する

```js
// postcss.config.(m)js
const config = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {}, // ここ
  },
};

export default config;
```

---

### 参考になるサイト

入門系

- [Tailwind CSS 入門と実践](https://zenn.dev/yohei_watanabe/books/c0b573713734b9/viewer/fac5ab)

- [利用者爆増中 初めてでもわかるTailwind CSS入門 基礎編](https://reffect.co.jp/html/tailwindcss-for-beginners#Tailwind_CSS)

- [Tailwind CSS実践入門](https://gihyo.jp/article/2023/07/tailwindcss-practice-02)