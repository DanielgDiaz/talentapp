<template>
  <label>Country</label>
  <select v-model="country">
    <option v-for="country in countries" :key="country.value">
      {{ country.label }}
    </option>
  </select>
</template>

<script>
const countries = require("i18n-iso-countries");
countries.registerLocale(require("i18n-iso-countries/langs/en.json"));
export default {
  name: "CountrySelection",
  computed: {
    countries() {
      const list = countries.getNames("en", { select: "official" });
      return Object.keys(list).map((key) => ({ value: key, label: list[key] }));
    },
  },
  data() {
    return {
      selected: null,
    };
  },
};
</script>
