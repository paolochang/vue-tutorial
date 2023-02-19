<template>
  <div class="container">
    <div class="block">
      <label for="province">Province</label>
      <select
        name=""
        id="province"
        @change="changeProvince($event)"
        v-model="selectedProvince"
      >
        <option value="">Select Province</option>
        <option
          :value="province.code"
          :key="province.name"
          v-for="province in provinces"
        >
          {{ province.name }}
        </option>
      </select>
    </div>
    <div class="block">
      <label for="city">City </label>
      <select name="" id="city">
        <option
          :value="city.name"
          :key="city.name"
          v-for="city in selectedCities"
        >
          {{ city.name }}
        </option>
      </select>
    </div>
    <small>with onChange changeProvince handler</small>
    <div class="block">
      <label for="city">City </label>
      <select name="" id="city">
        <option
          :value="city.name"
          :key="city.name"
          v-for="city in cities.filter(
            (city) => city.province === selectedProvince
          )"
        >
          {{ city.name }}
        </option>
      </select>
    </div>
    <small>with inline filter</small>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      selectedProvince: '',
      provinces: [
        { code: 'ab', name: 'Alberta' },
        { code: 'bc', name: 'British Columbia' },
        { code: 'mb', name: 'Manitoba' },
        { code: 'nb', name: 'New Brunswick' },
        { code: 'nl', name: 'Newfoundland and Labrador' },
        { code: 'nw', name: 'Northwest Territories' },
        { code: 'ns', name: 'Nova Scotia' },
        { code: 'nu', name: 'Nunavut' },
        { code: 'on', name: 'Ontario' },
        { code: 'qc', name: 'Québec' }
      ],
      cities: [
        { province: 'ab', name: 'Calgary' },
        { province: 'ab', name: 'Edmonton' },
        { province: 'ab', name: 'Red Deer' },
        { province: 'ab', name: 'St. Albert' },
        { province: 'ab', name: 'Grande Prairie' },
        { province: 'ab', name: 'Medicine Hat' },
        { province: 'ab', name: 'Airdrie' },
        { province: 'ab', name: 'Lethbridge' },
        { province: 'ab', name: 'Canmore' },
        { province: 'bc', name: 'Vancouver' },
        { province: 'bc', name: 'Victoria' },
        { province: 'bc', name: 'Nanaimo' },
        { province: 'bc', name: 'Kelowna' },
        { province: 'bc', name: 'Kamloops' },
        { province: 'bc', name: 'Penticton' },
        { province: 'bc', name: 'Coquitlam' },
        { province: 'bc', name: 'Burnaby' },
        { province: 'bc', name: 'Abbotsford' },
        { province: 'mb', name: 'Winnipeg' },
        { province: 'mb', name: 'Brandon' },
        { province: 'mb', name: 'Portage la Prairie' },
        { province: 'mb', name: 'Selkirk' },
        { province: 'mb', name: 'Morden' },
        { province: 'mb', name: 'Dauphin' },
        { province: 'mb', name: 'Steinbach' },
        { province: 'mb', name: 'The Pas' },
        { province: 'mb', name: 'Flin Flon' },
        { province: 'nb', name: 'Saint John' },
        { province: 'nb', name: 'Moncton' },
        { province: 'nb', name: 'Edmundston' },
        { province: 'nb', name: 'Fredericton' },
        { province: 'nb', name: 'Bathurst' },
        { province: 'nb', name: 'Dieppe' },
        { province: 'nb', name: 'Miramichi' },
        { province: 'nb', name: 'Campbellton' },
        { province: 'nb', name: 'Grand Falls' },
        { province: 'nl', name: "St. John's" },
        { province: 'nl', name: 'Corner Brook' },
        { province: 'nl', name: 'Labrador City' },
        { province: 'nl', name: 'Happy Valley-Goose Bay' },
        { province: 'nl', name: 'Mount Pearl' },
        { province: 'nl', name: 'Deer Lake' },
        { province: 'nl', name: 'Paradise' },
        { province: 'nl', name: 'Channel-Port aux Basques' },
        { province: 'nl', name: 'Gander' },
        { province: 'nw', name: 'Yellowknife' },
        { province: 'nw', name: 'Fort Smith' },
        { province: 'nw', name: 'Inuvik' },
        { province: 'nw', name: 'Fort Simpson' },
        { province: 'nw', name: 'Déline' },
        { province: 'nw', name: 'Norman Wells' },
        { province: 'nw', name: 'Hay River' },
        { province: 'nw', name: 'Tuktoyaktuk' },
        { province: 'nw', name: 'Fort McPherson' },
        { province: 'ns', name: 'Halifax Regional Municipality' },
        { province: 'ns', name: 'New Glasgow' },
        { province: 'ns', name: 'Halifax' },
        { province: 'ns', name: 'Truro' },
        { province: 'ns', name: 'Lunenburg' },
        { province: 'ns', name: 'Yarmouth' },
        { province: 'ns', name: 'Amherst' },
        { province: 'ns', name: 'Antigonish' },
        { province: 'ns', name: 'Wolfville' },
        { province: 'nu', name: 'Iqaluit' },
        { province: 'nu', name: 'Pangnirtung' },
        { province: 'nu', name: 'Gjoa Haven' },
        { province: 'nu', name: 'Arviat' },
        { province: 'nu', name: 'Rankin Inlet' },
        { province: 'nu', name: 'Kugluktuk' },
        { province: 'nu', name: 'Pond Inlet' },
        { province: 'nu', name: 'Cambridge Bay' },
        { province: 'nu', name: 'Igloolik' },
        { province: 'on', name: 'Toronto' },
        { province: 'on', name: 'Ottawa' },
        { province: 'on', name: 'Windsor' },
        { province: 'on', name: 'Guelph' },
        { province: 'on', name: 'Kingston' },
        { province: 'on', name: 'Hamilton' },
        { province: 'on', name: 'Mississauga' },
        { province: 'on', name: 'Burlington' },
        { province: 'on', name: 'Waterloo' },
        { province: 'qc', name: 'Québec City' },
        { province: 'qc', name: 'Montreal' },
        { province: 'qc', name: 'Levis' },
        { province: 'qc', name: 'Gatineau' },
        { province: 'qc', name: 'Sherbrooke' },
        { province: 'qc', name: 'Trois-Rivières' },
        { province: 'qc', name: 'Laval' },
        { province: 'qc', name: 'Rivière-du-Loup' },
        { province: 'qc', name: 'Thetford Mines' }
      ],
      selectedCities: []
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    changeProvince(event) {
      console.log(event.target.value)
      this.selectedCities = this.cities.filter(
        (city) => city.province === this.selectedProvince
      )
    }
  }
}
</script>

<style scoped>
.container {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 300px;
}
.block {
  display: flex;
  justify-content: space-between;
  margin: 10px 0;
}
</style>
