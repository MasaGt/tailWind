### tailwind　にて複数の背景を設定する方法


一番簡単なのは　tailwind.config.js にて backgrund~~ の項目を拡張すること

```js
// tailwind.config.js
import type { Config } from "tailwindcss";

const config: Config = {
  content: [
  ],
  theme: {
    extend: {
      backgroundImage: {
        "multi-backgound-img": "url(image1), url(image2)",
      },
      backgroundSize: {
        "multi-backgound-img": "~px ~px, ~px ~px",
      },
      backgroudPosition: {
        "multi-backgound-img": "0 0, right bottom",
      },
    },
  },
  plugins: [],
};
export default config;
```

<br>

config ファイルを編集後は bg-~~ で利用可能

```js
// .(j|t)sx
<div className="bg-multi-backgound-img">
</div>
```

---

### 複数のグラデーションを背景に設定する方法

同様に tailwind 設定ファイルにて background 系のプロパティを拡張する

```

// tailwind.config.js
import type { Config } from "tailwindcss";

const config: Config = {
  content: [
  ],
  theme: {
    extend: {
      backgroundImage: {
        "gradient": "linear-gradient(rgba(255, 0, 0, 0.5), rgba(0, 255, 0, 0.5), rgba(0, 0, 255, 0.5)), linear-gradient(90deg, rgba(0,0,0, 0.5), rgba(255, 255, 255, 0.5))"
",
      },
    },
  },
  plugins: [],
};
export default config;
```

<br>

利用する際は bg-~ で参照

```js
// .(j|t)sx
<div className="bg-gradient">
</div>
```
