<template>
  <div>
    <div>
      <input type="checkbox" id="html" value="HTML" v-model="favoriteLang" />
      <label for="html">HTML</label>
    </div>
    <div>
      <input type="checkbox" id="css" value="CSS" v-model="favoriteLang" />
      <label for="css">CSS</label>
    </div>
    <div>
      <input type="checkbox" id="js" value="JS" v-model="favoriteLang" />
      <label for="js">JavaScript</label>
    </div>
    <div>Selected: {{ favoriteLang }}</div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      favoriteLang: []
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {}
}
</script>
