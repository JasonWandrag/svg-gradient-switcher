<template>
  <component :is="type"></component>
</template>

<script>
import * as components from "./patterns/index";

export default {
  components: {
    ...components,
  },

  props: {
    type: { type: String, required: true },
  },
};
</script>
