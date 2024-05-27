### tailwind で独自の アニメーションを定義する方法

tailwind.config にて拡張する

```js
// tailwind.config.js
const config: Config = {
  theme: {
    keyframes:
     keyframes名: {
        "x%": { cssプロパティ: "設定値" },
        "z%": { cssプロパティ: "設定値",  cssプロパティ: "設定値"  },
     },
     animation: {
        animation名: "keyframes名 duration delay など",
     }
  }
};
export default config;
```

<br>

コンポーネント側で利用する際は animate-animation名でクラス名を指定する

```js
<div className="animate-animation名">
animated!
</div>
```

---

### 利用例
まずは tailwind 設定ファイルをカスタマイズ

```js
// tailwind.config.js
const config: Config = {
  theme: {
    keyframes:
     appear: {
        "0%": { transform: "translate(-100%)" },
        "100%": { transform: "translate(0%)"  },
     },
     animation: {
        appear: "appear 1s 0.5s infinite"
     }
  }
};
export default config;
```

<br>

コンポーネント側でアニメーションの適用を行う

```js
<div className="animation-appear bg-stale-200 w-fit h-fit">
Hello!
</div>
```

<img src="./img/animation_1.gif" />

---

### tranform-origin の設定について

tailwind.config の keyframes で transform-origin の指定をしたい場合は以下の点に注意すること

<br>

**transform-origin は正しいプロパティ名ではない**

- \*CSS では正しいプロパティ名だが、tailwind.config.tsでは間違い

```js
theme: {
    keyframes: {
        "0%": { transform: "scale(0)", transform-origin: "right"},
        "100%": { transform: "scale(1)", transform-origin: "right"}
    },
    animation: {
        appear: "appear ~~"
    }
}
```

<br>

**ただしくは transformOrigin**

```js
theme: {
    keyframes: {
        "0%": { transform: "scale(0)", transformOrigin: "right"},
        "100%": { transform: "scale(1)", transformOrigin: "right"}
    },
    animation: {
        appear: "appear ~~"
    }
}
```

<img src="./img/animation_2.gif" />