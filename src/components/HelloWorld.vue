<template>
  <h1>{{ msg }}</h1>
  <button
    @click="count++"
    @blur="test"
  >
    count is: {{ count }}
  </button>
  <p>Edit <code>components/HelloWorld.vue</code> to test hot module replacement.</p>
  <p>hello vite</p>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: {
      default: '',
      type: String,
    },
  },
  data() {
    return {
      count: 0,
    }
  },
}
</script>
<style lang="scss" scoped>
p{
  background: #f00;
}
</style>
