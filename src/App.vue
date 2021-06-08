<template>
  <div class="all-dropdown-container">
    <div
      class="dropdown-with-label"
      v-for="(dropdown, index) in dropdowns"
      :key="index"
      v-show="dropdown.isShow"
    >
      <div class="dropdown-label">
        <span>Choose {{ dropdown.label }}:</span>
        <span class="gg-arrow-long-right"></span>
      </div>
      <Dropdown
        class="dropdown-container"
        :ref="`dropdown-${index}`"
        @selected="(data) => seleteData(data, index)"
        :defaultSelected="'ab'"
        :options="dropdown.options"
      />
    </div>
  </div>
</template>

<script>
import Dropdown from "./components/Dropdown.vue";

const years = [
  {
    name: "1996",
    id: "1996",
  },
  {
    name: "1997",
    id: "1997",
  },
  {
    name: "1998",
    id: "1998",
  },
  {
    name: "1999",
    id: "1999",
  },
  {
    name: "2000",
    id: "2000",
  },
  {
    name: "2001",
    id: "2001",
  },
  {
    name: "2002",
    id: "2002",
  },
];

const make = [
  {
    name: "Honda",
    id: "Honda",
  },
  {
    name: "Toyota",
    id: "Toyota",
  },
  {
    name: "Yamaha",
    id: "Yamaha",
  },
  {
    name: "Mecerdes",
    id: "Mecerdes",
  },
  {
    name: "Porsche",
    id: "Porsche",
  },
  {
    name: "Audi",
    id: "Audi",
  },
  {
    name: "Aucura",
    id: "Aucura",
  },
];

const model = [
  {
    name: "accor",
    id: "accor",
  },
  {
    name: "civic",
    id: "civic",
  },
  {
    name: "city",
    id: "city",
  },
];

export default {
  name: "App",
  components: {
    Dropdown,
  },
  data() {
    return {
      dropdowns: [
        {
          label: "Year",
          options: years,
          isShow: true,
        },
        {
          label: "Make",
          options: make,
          isShow: false,
        },
        {
          label: "Model",
          options: model,
          isShow: false,
        },
      ],
    };
  },
  computed: {},
  methods: {
    seleteData(data, index) {
      console.log(data);
      if (this.dropdowns[index + 1]) this.dropdowns[index + 1].isShow = true;
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.all-dropdown-container {
  margin: auto;
  .dropdown-with-label {
    display: flex;
    margin-top: 10px;
    .dropdown-label {
      vertical-align: middle;
      line-height: 29px;
      margin-right: 20px;
      width: 250px;
      span:nth-child(1) {
        margin-right: 20px;
      }
      .gg-arrow-long-right {
        box-sizing: border-box;
        position: relative;
        display: inline-block;
        transform: scale(var(--ggs, 1));
        border-top: 2px solid transparent;
        border-bottom: 2px solid transparent;
        box-shadow: inset 0 0 0 2px;
        width: 100px;
        height: 10px;
      }
      .gg-arrow-long-right::after {
        content: "";
        display: block;
        box-sizing: border-box;
        position: absolute;
        width: 10px;
        height: 10px;
        border-top: 2px solid;
        border-right: 2px solid;
        transform: rotate(45deg);
        right: 0;
        bottom: -2px;
      }
    }
    .dropdown-container {
      vertical-align: middle;
    }
  }
}
</style>
