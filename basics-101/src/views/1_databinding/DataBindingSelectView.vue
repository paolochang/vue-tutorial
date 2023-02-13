<template>
  <div>
    <select name="" id="" v-model="selectedCity">
      <option value=""></option>
      <option value="02">Seoul</option>
      <option value="051">Busan</option>
      <option value="064">Jeju</option>
    </select>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      selectedCity: '051'
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {}
}
</script>
