<template>
  <div>
    <div class="block">
      <input
        type="search"
        name=""
        id=""
        v-model="upperKeyword"
        @keydown="checkEnter($event)"
      />
      <button @click="searchUpperKeyword">Search</button>
    </div>
    <div class="block">
      <input
        type="search"
        name=""
        id=""
        v-model="lowerKeyword"
        @keydown.enter="searchLowerKeyword"
      />
      <button @click="searchLowerKeyword">Search</button>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      upperKeyword: '',
      lowerKeyword: ''
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    checkEnter(event) {
      if (event.keyCode === 13) {
        this.searchKeyword()
      }
    },
    searchUpperKeyword() {
      console.log(this.upperKeyword)
    },
    searchLowerKeyword() {
      console.log(this.lowerKeyword)
    }
  }
}
</script>

<style scoped>
.block {
  margin: 10px 0;
}
</style>
