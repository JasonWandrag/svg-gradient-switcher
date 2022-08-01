<template>
  <section>
    <div class="card">
      <h1>Some Pretty Text</h1>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped>
section {
  min-height: 100vh;
  padding: 30px;
  display: grid;
  place-content: center;
}

.card {
  padding: 30px;
}

h1 {
  text-transform: initial;
  border-bottom: 2px solid rgb(232, 231, 231);
  padding: 0;
}
</style>
