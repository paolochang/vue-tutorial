<template>
  <div>
    <div class="block">
      <label for="username">Two-way binding example</label>
      <br />
      <input type="text" id="username" v-model="username" />
      <button @click="buttonHandler">Print</button>
      <button @click="resetHandler">Reset</button>
    </div>
    <div class="block">
      <label>Input returns String type</label>
      <br />
      <input type="text" v-model="num1" /> +
      <input type="text" v-model="num2" /> =
      <span>{{ num1 + num2 }}</span>
    </div>
    <div class="block">
      <label>number type v-model on Input</label>
      <br />
      <input type="text" v-model.number="num3" /> +
      <input type="text" v-model.number="num4" /> =
      <span>{{ num3 + num4 }}</span>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      username: 'paolography',
      num1: 0,
      num2: 0,
      num3: 0,
      num4: 0
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    buttonHandler() {
      console.log(this.username)
    },
    resetHandler() {
      this.username = 'paolography'
      console.log(this.username)
    }
  }
}
</script>

<style scoped>
.block {
  margin-bottom: 1rem;
}
</style>
