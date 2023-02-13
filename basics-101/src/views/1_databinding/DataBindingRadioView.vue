<template>
  <div>
    <div>
      <input type="radio" id="toronto" value="Toronto" v-model="selected" />
      <label for="toronto">Toronto</label>
    </div>
    <div>
      <input
        type="radio"
        id="mississauga"
        value="Mississauga"
        v-model="selected"
      />
      <label for="mississauga">Mississauga</label>
    </div>
    <div>
      <input type="radio" id="markham" value="Markham" v-model="selected" />
      <label for="markham">Markham</label>
    </div>
    <div>Selected: {{ selected }}</div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      selected: 'Toronto'
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {}
}
</script>
