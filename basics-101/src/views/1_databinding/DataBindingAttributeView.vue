<template>
  <div>
    <div class="block">
      <label
        ><span class="code">v-bind:value="username"</span> is One-way
        binding</label
      >
      <br />
      <input type="text" name="" id="" v-bind:value="username" readonly />
    </div>
    <div class="block">
      <label>
        <span class="code">v-bind:value="username"</span> can be shorten as
        <span class="code">:value="username"</span></label
      >
      <br />
      <input type="text" name="" id="" :value="username" readonly />
    </div>
    <div class="block">
      <label for="vue-logo"
        >Image source data-binding with imgSrc variable</label
      >
      <br />
      <img
        :src="imgSrc"
        id="vue-logo"
        alt="Vue Logo"
        style="width: 100px; height: auto"
      />
    </div>
    <div class="block">
      <label
        >Search disabled data-binding with condition: keyword not to be
        empty</label
      >
      <br />
      <input type="search" name="" id="" v-model="keyword" />
      <button :disabled="keyword === ''">Search</button>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      username: 'paolography',
      imgSrc: 'https://www.vectorlogo.zone/logos/vuejs/vuejs-ar21.png',
      keyword: ''
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {}
}
</script>

<style scoped>
.block {
  margin-bottom: 1rem;
}
label {
  display: inline-block;
  margin-bottom: 5px;
}
.code {
  padding: 0.5px 4px;
  border-radius: 10px;
  color: white;
  font-weight: 600;
  background-color: lightcoral;
}
</style>
