<template>
  <div class="card">
    <label>
      Pick a background color:
      <!-- <select v-model="chosen" @change="gradientPicker">
        <option v-for="gradient of gradients" :key="gradient" :value="gradient">
          {{ gradient }}
        </option>
      </select> -->
      <!-- <input type="color" v-model="color" @change="pickColor" /> -->
      <input
        type="range"
        min="0"
        max="360"
        v-model="hue"
        step="15"
        @change="pickHue"
      />
    </label>
  </div>
</template>

<script>
export default {
  data() {
    return {
      gradients: [
        "early-sunset",
        "early-sunrise",
        "vibrant-shadow",
        "valentines-day",
        "gypsy-owl",
        "digital-pander",
        "mango-blast",
      ],
      chosen: "early-sunset",
      chosen: "color",
      hue: 0,
    };
  },
  methods: {
    gradientPicker() {
      document.querySelector("body").style.background = `var(--${this.chosen})`;
      // document
      //   .querySelector(":root")
      //   .style.setProperty("--gradient", `var(--${this.chosen})`);
    },
    pickColor() {
      document.querySelector("body").style.background = this.color;
    },
    pickHue() {
      console.log(this.hue);
      let hue = parseInt(this.hue);
      document.querySelector(
        "body"
      ).style.background = `hsl(${hue}, 100%, 80%)`;
    },
  },
};
</script>

<style></style>
