<template>
  <div>
    <button @click="increaseCounter">+ 1</button>
    <button @click="decreaseCounter">- 1</button>
    <p>{{ counter }}</p>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      counter: 0
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    increaseCounter() {
      this.counter += 1
    },
    decreaseCounter() {
      this.counter -= 1
    }
  }
}
</script>

<style scoped>
button {
  margin: 0 10px;
}
</style>
