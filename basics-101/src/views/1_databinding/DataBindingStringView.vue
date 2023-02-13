<template>
  <div>
    <h1>Hello {{ userName }}</h1>
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userName: 'John Doe',
      message: 'Welcome to Vue Tutorial',
      arr: [],
      obj: {}
    }
  }
}
</script>

<style scoped>
h1 {
  color: #ff6347;
}
</style>
