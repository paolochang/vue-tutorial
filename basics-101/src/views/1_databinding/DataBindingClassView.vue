<template>
  <div>
    <div class="block">
      <input
        type="checkbox"
        name=""
        id="class-binding-example"
        v-model="isActive"
      />
      <label
        for="class-binding-example"
        :class="{ 'text-red': hasError, active: isActive }"
      >
        Class binding example:
        {{ isActive === true ? 'active' : 'inactive' }}</label
      >
    </div>
    <div class="block">
      <span :class="styleArray"
        >Class binding with an array, styleArray: {{ styleArray }}</span
      >
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      isActive: false,
      hasError: false,
      styleArray: ['active', 'text-red']
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
  margin-bottom: 10px;
}
.active {
  background-color: greenyellow;
  font-weight: bold;
}
.text-red {
  color: red;
}
</style>
