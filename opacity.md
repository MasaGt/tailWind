### opacity の設定方法

2つの方法がある

1. opacity: 1 のような設定方法
    - opacity-\[value\] 
    - value は 10 で 10% (10% = opacity: .1)。 100 で 100% (100% = opacity: 1)

<br>

\*子要素のpタグにもopacityが適用されてしまうので注意

```ts
// 50% = 0.5 の opacity を適用したい
<div className="opacity-50">
    <p>hello, world!</p>
</div>
```

<br>

2. rgba のような設定方法
    - bg-\[color\]/\[opacity value\]

<br> 

\* 以下の方法だと、子要素に親要素の opacity は適用されない

```ts
// 同じように50%の opacity を適用したい
<div className="bg-wite/50">
    <p>hello, world!</p>
</div>
```