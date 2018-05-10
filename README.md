效果

![Alt text](http://p5qgrn52w.bkt.clouddn.com/ColorfulButton/t010026c94de05c9e8e.gif)

安装
```
npm i -save colorful-button
或
yarn add colorful-button
```
使用
```
<template>
  <ColorfulButton class="login-box" @onClick="login" text="登陆"></ColorfulButton>
</template>

<script>
  import WaterRipple from 'waterripple'
  export default {
    components: {
      WaterRipple
    },
    methods: {
      login (password) {
        console.log('点击了！')
      }
    }
  }
</script>

<style scoped>
  .login-box {
      height: 400px;
      width: 500px;
      background-color: rgba(0, 0, 0, 0.2);
      position: absolute;
      left: 0;
      right: 0;
      top: 0;
      bottom: 0;
      margin: auto;
    }
</style>
```
