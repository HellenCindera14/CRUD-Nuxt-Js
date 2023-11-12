<template>
  <div>
    <div class="spinner-border text-primary" role="status">
      <span class="visually-hidden">Loading...</span>
    </div> {{ title }}...
  </div>
</template>

<script lang="ts">
import type { create } from "domain";

export default {
  name: "Loading",
  props: {
    title: String,
  },
};
</script>
