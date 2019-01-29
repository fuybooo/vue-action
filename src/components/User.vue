<template>
  <div>
    <h1 :class="{'is-active': active}">用户: {{userName}}</h1>
    <div v-if="seen">{{text}}</div>
    <button v-on:click="doSomething">改变数据显隐和逆转消息</button>
    <button v-on:click="say">say</button>
    <div>{{reverseMsg}}</div>
    <ol>
      <li :key="todo.text" v-for="todo in todos">{{todo.text}}</li>
    </ol>
    <div></div>
    <input type="text" @keyup.enter="submitBill">
    <div>
      <input type="number" v-model.number="n">
    </div>
  </div>
</template>

<script>
  const config = {
    name: "User",
    data: function () {
      return ({
        userName: '44',
        seen: true,
        todos: [
          {text: '学习vue'},
          {text: '学习es6'},
          {text: '学习怎么做人'},
        ],
        text: '请点击按钮切换我的正反显示',
        doSomething: () => {
          this.text = '改变了哦';
          this.active = !this.active;
          this.n++;
        },
        active: true,
        n: 4
      })
    },
    computed: {
      reverseMsg: function () {
        return this.text.split('').reverse().join('');
      }
    },
    watch: {
      text: function () {
        const d = new Date();
        this.text = this.text.slice(0, -4) + ('0' + d.getSeconds()).slice(-2);
      }
    },
    methods: {
      say: function () {
        console.log(this.text);
      },
      submitBill: function () {

      }
    }
  };

  export default config;
</script>

<style scoped>
  h1 {
    color: red;
  }

  .is-active {
    color: #000;
  }
</style>
