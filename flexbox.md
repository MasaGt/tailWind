### Flexbox　レイアウトを利用する際の注意点

Flexbox の要素を並べる方向を縦 (column) にしたいとき

- flex と flex-col の両方のクラス名を設定する必要がある
    - flex-col　だけではだめ

```ts
// .(t|j)sx
<div className="flex flex-col">
    <div>item1</div>
    <div>item2</div>
    ...
</div>
```