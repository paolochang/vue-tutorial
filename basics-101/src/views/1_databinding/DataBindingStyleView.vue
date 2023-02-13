<template>
  <div>
    <div style="color: red; font-size: 30px">
      <span>Inline Style: color:red, font-size: 30px</span>
    </div>
    <div :style="style2">
      <span>Style binding: color:red, font-size: 30px</span>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      style2: {
        color: 'green',
        fontSize: '30px'
      }
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {}
}
</script>
