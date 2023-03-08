<template>
  {{ $route.params.id }}
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return { servers: {} };
  },
});
</script>

<style lang="scss"></style>
