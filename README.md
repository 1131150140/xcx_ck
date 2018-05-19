1.新增页面需要npm run dev重启一下。

2.小程序里所有的 BOM／DOM 都不能用，也就是说 v-html 指令不能用。

3.暂不支持在组件上使用 Class 与 Style 绑定，需要在组件内部书写。

4.mpvue 可以支持小程序的原生组件，比如： picker,map 等，需要注意的是原生组件上的事件绑定，需要以 vue 的事件绑定语法来绑定，如 bindchange="eventName" 事件，需要写成 @change="eventName"。

5.mpvue 建议使用 v-model.lazy 绑定方式以优化性能，此外 v-model 在老基础库下输入框输入时可能存在光标重设的问题。 

6.写页面跳转时候传入动态参数，需要写成:url，如：<navigator url="'../test/main?id='+id hover-class="none""。

7.通过 this.$root.$mp.query 进行获取小程序在 page onLoad 时候传递的 options。通过 this.$root.$mp.appOptions 进行获取小程序在 app onLaunch/onShow 时候传递的 options。

8.使用this.$root.$mp.query获取参数需要在monted中获取，在created中会报Cannot read property 'query' of undefined 。