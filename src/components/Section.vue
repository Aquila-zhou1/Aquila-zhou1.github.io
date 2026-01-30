<!-- src/components/Section.vue -->
<template>
  <section :id="id" class="section">
    <h2>{{ title }}</h2>
    <div class="section-body">
      <slot />
    </div>
  </section>
</template>

<script setup lang="ts">
const props = defineProps<{
  id?: string;
  title: string;
}>();
</script>

<style scoped>
.section {
  margin-top: 1.5em;
}

.section h2 {
  margin-top: 1.5em;
  padding-bottom: 0.3em;
  border-bottom: 2px solid #eaeaea;
}

.section-body {
  margin-top: 0.3em;
}
</style>
