# vue-initi
这是一个通过Vue directive来实现在加载之前通过占位来保持布局状态的插件


# Install
Using `yarn` or `npm` to install `vue-initi`:

```
# yarn
yarn add vue-initi

# npm
npm install vue-initi
```

# Usage
In your `main.js` file:

```
import VueIniti from 'vue-initi'

Vue.use(VueIniti)
```

Now `vue-initi` is a global Vue directive, you can use `v-initi` in every `.vue` file.

# Params

|  param |   type   | description | necessary |
| ------ | -------- | ----------- | --------- |
|  data  | {Object} | the data you bind to the node | Yes |
| config | {Object} | the color lump's css config | No |

可执行例子:

```
<template>
  <div id="app" style="width:200px;height:50px;">
    <div v-initi="{ data: content, config }"></div>
    <img v-initi="{ data: src, config: {width: '100px',height: '100px',borderRadius: '50%'}}">
  </div>
</template>

<script>
export default {
  data () {
    return {
      src: '',
      content: '',
      config: {
        width: '200px',
        height: '18px',
        background: '#ddd'
      }
    }
  },
  mounted () {
    setTimeout(()=>{
        this.content = 'Hello world！';
	this.src = 'https://www.baidu.com/img/baidu_jgylogo3.gif';
    })
  }
}
</script>
```

And the note with `v-initi` will be like this:

```
<div v-initi="{ data: content, config }">
  <div style="width: 100%; height: 100%; background: #eee;></div>
</div>
```

# Lisence
MIT