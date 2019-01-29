<template>
  <div>
    <div><label>propA:</label><span>{{propA}}</span></div>
    <div><label>propB:</label><span>{{propB}}</span></div>
    <div><label>propC:</label><span>{{propC}}</span></div>
    <div><label>propD:</label><span>{{propD}}</span></div>
    <div><label>propE:</label><span>{{propE}}</span></div>
    <div><label>propF:</label><span>{{propF}}</span></div>
    <div><label>propG:</label><span>{{propG}}</span></div>
    <div><label>propH:</label><span>{{propH}}</span></div>
  </div>
</template>

<script>
  export default {
    name: "test-props",
    props: {
      propA: String,
      propB: Number,
      propC: Object,
      propD: Boolean,
      propE: [String, Number],
      propF: {
        type: String,
        required: true
      },
      propG: {
        type: Object,
        default: function () {
          return {
            message: 'message!'
          }
        }
      },
      propH: {
        type: String,
        validator: function (v) {
          return ['a', 'b', 'c'].includes(v)
        }
      }
    }
  }
</script>

<style scoped>

</style>
