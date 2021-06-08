<template>
  <div class="app">
    <img style="margin-bottom: 20px" :src="'./2.jpg'" />
    <MultipleDropdown />
    <img style="margin-top: 20px" :src="'./1.jpg'" />
  </div>
</template>

<script>
import MultipleDropdown from "./components/MultipleDropdown.vue";

export default {
  name: "App",
  components: {
    MultipleDropdown,
  },
  computed: {},
  methods: {},
};
</script>

<style scoped>
.app {
  background: white;
}
</style>
