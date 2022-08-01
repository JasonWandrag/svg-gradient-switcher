<template>
  <div class="card">
    <label>
      Pick a background pattern:
      <select @change="patternPicker" v-model="chosen">
        <option
          v-for="pattern of pat"
          :key="pattern.name"
          :value="pattern.name"
        >
          {{ pattern.name }}
        </option>
      </select>
    </label>
  </div>
</template>

<script>
import svgList from "../assets/patterns/index";
import Patterns from "./Patterns.vue";

console.log(svgList);

const { svg_sizes } = svgList;
const patternContainer = document.querySelector("#pattern");

export default {
  data() {
    return {
      pat: Object.keys(svgList).map((key) => {
        return { source: svgList[key], name: key };
      }),
      chosen: "",
    };
  },
  methods: {
    async patternPicker() {
      let s = this.chosen
        .replace(/([A-Z])/g, " $1")
        .trim()
        .toLowerCase()
        .split(" ")
        .join("_");
      let chosenSize = 0;
      for (let size in svg_sizes) {
        if (svg_sizes[size][s]) {
          chosenSize = size;
        }
      }
      patternContainer.style.background = `url(${svgList[s]}) center / ${chosenSize}px fixed`;
    },
  },
  components: { Patterns },
  mounted() {
    console.log(this.pat);
  },
};
</script>

<style scoped></style>
