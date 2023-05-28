# Vue.js

## 前提

- バージョン：3以上

## 用語

|      項目       |                                                     内容                                                     |
| --------------- | ------------------------------------------------------------------------------------------------------------ |
| ディレクティブ  | v-〜で始まる特別な属性のこと(directive(指令))。Vue.jsに何らかの指示を渡すための仕組み。                      |
| Options API     | data、methods、mountedなどのオプションから１つのオブジェクトを用いてコンポーネントのロジックを定義する方法。 |
| Composition API | インポートした各種API関数を使ってコンポーネントのロジックを定義する方法。                                    |
| リアクティブ    |                                                                                                              |

## 使用方法

1. CDNからの取得
1. npmコマンドによるインストール
1. vue-cliによる雛形作成

### CDNからの取得

### npmコマンドによるインストール

### vue-cliによる雛形作成

## ディレクティブ

|              項目              | 記載方法 |   省略系    |                     サンプル                     |                      備考                       |
| ------------------------------ | -------- | ----------- | ------------------------------------------------ | ----------------------------------------------- |
| データアクセス                 | v-text   | {{ 値 }}    | `<p v-text="値"></p>` or                         | `<p>{{ 値 }}</p>`でも省略可能                   |
| 属性値にJavaScript式を埋め込む | v-bind   | :属性名     | `<a v-bind:href="値">リンク</a>`                 | v-bind:属性値="値"                              |
| 双方向データバインディング     | v-model  | -           | `<input v-model="値>`                            | inputタグ、selectタグ、textareaタグが使用可能。 |
| イベント                       | v-on     | @イベント名 | `<input v-on:イベント名="式">`                   |                                                 |
| if文                           | v-if     | -           | `<p v-if="値"></p>`                              | 条件に合致しないときは要素が削除される。        |
| 表示の切り替え                 | v-show   | -           | `<p v-show="値"></p>`                            | 「display:none」の切り替えを行っている。        |
| 繰り返し                       | v-for    | -           | `<p v-for="配列要素 in 配列" :key="一意のキー">` |                                                 |
| 式の無効化                     | v-pre    | -           | `<p v-pre>{{ 値 }}</p>`                          |                                                 |
| HTML埋め込み                   | v-html   | -           | `<p v-html="値"></p>`                            |                                                 |

## Component

### 基本的な使用法

```vue
<div id="app">
    <comp></comp>
</div>

<script>
const { createApp } = Vue

    createApp({
    })
    .component('comp', {
        template: `
            <h2>Component Area</h2>
        `
    })
    .mount('#app')
</script>
```

上記は１ファイルにコンポーネントを記載しているが、基本的には別ファイルにコンポーネントを定義する。

```vue
【Main】
<div id="app">
    <comp-tag></comp-tag>
</div>

<script type="module">
    const { createApp } = Vue
    import CompTag from './component.js'

    createApp({
        components: {
            CompTag
        },
    })
    .mount('#app')
</script>

【component】
export default{
    template: `
        <h2>Component Area from JS file</h2>
    `
}
```

### props

Componentに値を渡す。

```vue
【Main】
<div id="app">
    <comp-tag v-bind:msg="mainMessage"></comp-tag>
</div>

<script type="module">
    const { createApp } = Vue
    import CompTag from './props.js'

    createApp({
        components: {
            CompTag
        },
        data(){
            return{
                mainMessage: 'Component Area From Main Via Props'
            }
        }
    })
    .mount('#app')
</script>

【component】
export default{
    props:{
        msg: String
    },
    template: `
        <h2>{{ msg }}</h2>
    `
}
```
