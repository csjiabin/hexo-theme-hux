---
title: 使用vue-worker轻松使用Vue.js
date: 2018-09-05 15:56:03
catalog: false
author: "CSjiabin"
tags:
  - vue
---

> 像许多开发人员一样，当Web Workers首次出现在Web开发环境中时，我非常热情，并且对我可以用它们完成的各种惊人事情感到厌烦。然而，当我意识到工作人员必须从托管在Web服务器上的单独文件加载时，我的热情很快就受到了打击。这似乎是一个巨大的痛苦，不值得努力。结合API开销，自从我第一次尝试到现在为止，我还没有真正再次使用过工作者。看着`vue-worker`，我突然惊讶于我的Vue.js应用程序可以通过一个简单的API和没有外部文件来完成什么。

[vue-worker](https://github.com/israelss/vue-worker)（或者说是同一 [作者](https://github.com/israelss) 的 [simple-web-worker](https://github.com/israelss/simple-web-worker) ）的核心前提是Web Workers可以从Data URI初始化，它可以只是一个字符串化的函数。

`vue-worker`通过一个简单易懂的API来解决其中涉及的复杂性，允许您像promises一样轻松执行多头函数。

### 安装
通过 **Yarn** 或 **NPM** 安装`vue-worker`：
```shell
# Yarn
$ yarn add vue-worker

# NPM
$ npm install vue-worker --save
```
现在，启用`VueWorker`插件：
```js
// src/main.js
import Vue from 'vue';
import VueWorker from 'vue-worker';
import App from 'App.vue';

Vue.use(VueWorker);

new Vue({
  el: '#app',
  render: h => h(App)
});
```
这使您的组件能够访问`this.$worker`。

### 在Worker中运行函数
现在，您可以在组件内部使用`this.$worker.run(function, args[])`。

这运行一个输出 **Hello，World** 的函数！在组件安装时的工作线程中：
```html
<script>
export default {
  mounted() {
    this.$worker.run((arg) => {
      return `Hello, ${arg}!`
    }, ['World'])
    .then(result => {
      console.log(result)
    })
    .catch(e => {
      console.error(e)
    })
  }
}
</script>
```

### 可重复使用 Workers
您可以创建可重复使用的`worker` 代理 `this.$worker.create([{message, func}])`
```html
<script>
export default {
  data() {
    return {
      myWorker: null
    }
  },

  created() {
    this.myWorker = this.$worker.create([
      {message: 'message1', func: (arg) => `Output 1 ${arg}`},
      {message: 'message2', func: () => 'Output 2'}
    ])

    this.myWorker.postMessage('message1', ['Boop!'])
    .then(result => {
      console.log(result)
    })
  }
}
</script>
```
你还可以做更多的事情，看看`vue-worker`和`simple-worker`文档。