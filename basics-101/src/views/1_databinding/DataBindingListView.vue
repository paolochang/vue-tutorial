<template>
  <div>
    <div class="block">
      <label
        >Add key to option tag while using
        <span class="code">v-for="city in cities"</span></label
      >
      <select>
        <option value="">Select</option>
        <option :key="city.code" :value="city.code" v-for="city in cities">
          {{ city.name }}
        </option>
      </select>
    </div>
    <div class="block">
      <table>
        <thead>
          <tr>
            <th>No</th>
            <th>Name</th>
            <th>Price</th>
            <th>Order</th>
            <th>Total</th>
          </tr>
        </thead>
        <tbody>
          <tr :key="drink.id" v-for="drink in drinks">
            <td>{{ drink.id }}</td>
            <td>{{ drink.name }}</td>
            <td>{{ drink.price }}</td>
            <td><input type="number" v-model="drink.qty" min="0" /></td>
            <td>${{ drink.price * drink.qty }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      cities: [
        { name: 'Seoul', code: '02' },
        { name: 'Busan', code: '051' },
        { name: 'Jeju', code: '064' }
      ],
      drinks: [
        { id: 1, name: 'Coca Cola', price: 1.25, qty: 1 },
        { id: 2, name: 'Fanta: Orange', price: 1.25, qty: 1 },
        { id: 3, name: 'Ginger Ale', price: 1.25, qty: 1 },
        { id: 4, name: 'Sprite', price: 1.25, qty: 1 },
        { id: 5, name: 'Gatorade', price: 2.25, qty: 1 }
      ]
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
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
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
