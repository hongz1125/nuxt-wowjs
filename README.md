# nuxt-wowjs
nuxt wowjs 使用方法

1、 npm install --save 
2、 在 pulgins目录 增加 vue-wow.js

```
import Vue from "vue";

const { WOW } = require("wowjs");
Vue.prototype.$wow = WOW

```
3、修改 nuxt.config.js 
```
  css: [
    "@/assets/animate.css"
  ],
```

4、在需要使用的组件上 增加入下代码

```
  watch: {
    $route: {
      handler: function(to, form) {
        if (process.browser) {
          this.$nextTick(() => {
            new this.$wow({
              live: true,
              offset: 0
            }).init();
          });
        }
      },
      immediate: true
    }
  },
```

5、刷新预览
