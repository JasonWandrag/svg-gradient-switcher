<template>
  <section>
    <div class="card">
      <h1>Welcome to Pattern Playground</h1>
    </div>
    <div class="cont">
      <GradientPicker />
      <PatternPicker />
    </div>
  </section>
</template>

<script>
import GradientPicker from "../components/GradientPicker.vue";
import PatternPicker from "../components/PatternPicker.vue";
// @ is an alias to /src
export default {
  name: "Home",
  components: { GradientPicker, PatternPicker },
};
</script>

<style>
h1 {
  /* border: 2px solid rgb(232, 231, 231); */
  font-family: "Arima Madurai", cursive;
  color: rgb(232, 231, 231);
  text-transform: uppercase;
  font-weight: 300;
  font-size: 2.2rem;
  padding: 30px;
}
h2 {
  color: rgb(232, 231, 231);
  padding: 30px;
  font-weight: 100;
}
.cont {
  display: flex;
  gap: 30px;
  justify-content: space-between;
}

.cont > * {
  flex-grow: 1;
}
</style>
