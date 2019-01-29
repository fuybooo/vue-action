<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="哈哈"/>
    <TestComponent v-bind:test-object="testObject"></TestComponent>
    <User/>
    <blog-content
      v-for="blog in blogs"
      v-bind:key="blog.id"
      v-bind:blog="blog"
      v-on:n-font="changeFont += $event"
      v-on:a-font="changeFontEvent"
      v-on:input="changeInput"
    ></blog-content>
    <input type="text" v-model="changeFont">
    <div>自定义输入框</div>
    <custom-input v-model="textCustom"></custom-input>
    <button v-on:click="consoleText">测试textCustom</button>
    <div>插槽信息案例</div>
    <slot-info>这是错误信息哦</slot-info>

    <h3>TEST PROPS</h3>
    <test-props
      v-bind:prop-a="lsdk"
    ></test-props>
  </div>
</template>

<script>
  import HelloWorld from './components/HelloWorld.vue'
  import User from './components/User'
  import TestComponent from './components/TestComponent'
  import BlogContent from './components/blog-content'
  import CustomInput from './components/custom-input'
  import SlotInfo from './components/slot-info'
  import TestProps from './components/test-props'

  export default {
    name: 'app',
    data: function () {
      return {
        testObject: {
          name: 'testObject',
        },
        textCustom: '',
        blogs: [
          {
            id: 1,
            name: 'name',
            time: '2015-01-02',
            desc: '这是第一篇博客'
          },
          {
            id: 2,
            name: 'name2',
            time: '2015-01-03',
            desc: '这是第二篇博客'
          },
        ],
        changeFont: 0
      }
    },
    methods: {
      // 这个时候子组件传出来的参数 font
      changeFontEvent: function (font) {
        this.changeFont += 10 * font;
      },
      changeInput: function (event) {
        console.log(event);
      },
      consoleText: function () {
        console.log(this.textCustom);
      }
    },
    components: {
      HelloWorld,
      User,
      TestComponent,
      BlogContent,
      CustomInput,
      SlotInfo,
      TestProps
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
