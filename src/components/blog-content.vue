<template>
  <div>
    <span>{{blog.name}}</span>
    <span>{{blog.time}}</span>
    <span>{{blog.desc}}</span>
    <button @click="emitEvent()">发送</button>
    <button @click="$emit('n-font', 1)">发送2</button>
    <button @click="$emit('a-font', 1)">发送3</button>
    <input type="text" v-bind:value="inputValue" v-on:input="$emit('input', $event.target.value)">
  </div>
</template>

<script>
  export default {
    name: "blog-content",
    props: ['blog', 'inputValue'],
    data: function () {
      return {
        inputValue2: ''
      }
    },
    methods: {
      emitEvent: function () {
        // $emit('font-size');
        console.log('如何发送呢')
      }
    }
  }
</script>

<style scoped>

</style>
