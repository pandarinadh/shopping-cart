<template>
  <span>
    {{
      this.prefix +
      Number.parseFloat(this.value * this.conversion).toFixed(this.precision)
    }}
  </span>
</template>

<script>
import { defineComponent } from "@vue/composition-api";

export default defineComponent({
  props: {
    value: Number,
    prefix: {
      type: String,
      default: "$",
    },
    precision: {
      type: Number,
      default: 2,
    },
    conversion: {
      type: Number,
      default: 1,
    },
  },
});
</script>
