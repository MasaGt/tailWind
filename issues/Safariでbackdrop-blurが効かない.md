### 事象

backdrop-blur を指定しても Safari 上ではブラーが反映されない

```jsx
<div className="backdrop-blur">...<div>
```

---

### 原因

- backdrop-blur は backdrop-filter: blur() を設定する項目

- Safari で backdrop-filter を有効化するには 2024/05 現在 -webkit- のプレフィックスを付ける必要がある

- Tailwind の backdrop-blur は -weblit- を付けない

---

### 解決策

1. Autoprefixer をインストールし、それにベンダープレフィックスを付与してもらう方法

2. 別途、独自のカスタムスタイルをTailwindに追加する
