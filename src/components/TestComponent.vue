<template>
  <div>
    <button @click="count++">按钮{{count}}</button>
    <div>
      {{testObject.name}}
    </div>
  </div>
</template>

<script>
  export default {
    name: "TestComponent",
    props: ['testObject'],
    data: function () {
      return {
        count: 0
      }
    }
  }
</script>

<style scoped>

</style>
