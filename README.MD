# 组件通信

## 快速原型开发

- 通过 `npm i @vue/cli -g` 搭建交互式的项目脚手架。
- 通过 `npm i @vue/cli + @vue/cli-service-global -g` 快速开始零配置原型开发。
- 通过 `vue serve App.vue` 的方式可以直接运行vue项目
- 一个运行时依赖 (@vue/cli-service)，该依赖：一个丰富的官方插件集合，集成了前端生态中最好的工具。
 可升级；
- 基于 webpack 构建，并带有合理的默认配置；
- 可以通过项目内的配置文件进行配置；
- 可以通过插件进行扩展。
- 一套完全图形化的创建和管理 Vue.js 项目的用户界面。

## 父级组件往子级组件传递数据
- 父级组件引用,注册,使用子级组件
- 父级组件定义数据
- 子级组件自定义属性,然后将父级组件的数据赋值给该属性
```html
<template>
  <div id="parent">
    parent：{{money}}
    <!-- 父级组件使用子级组件,并定义value属性,将父级组件money传递给子级 -->
    <Son1 :value="money"/>
  </div>
</template>
<script>
import Son1 from "./Son1"; // 父级组件引入子级组件
export default {
  name: "Parent",
  components: { Son1 },
  data() {
    return {
      money: 100
    };
  }
};
</script>
```

- 既然通过定义属性传递父级组件的数据,那么子级组件自然应该通过该自定义属性获取父亲传递过来的值(props)

```html
<template>
  <div id="son1">Son1:{{value}}</div>
</template>
<script>
export default {
  name: "Son1",
  props: { // 子级组件应该使用props:然后定义传递组件的数据类型和默认值
    value: {
      type: Number,
      default: 0
    }
  }
};
</script>
```

## 子级组件传值给父级组件的值

