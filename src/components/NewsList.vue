<!-- src/components/NewsList.vue -->
<template>
  <ul class="news-list">
    <li v-for="item in items" :key="item.date + item.text">
      <span class="news-date">[{{ item.date }}]:</span>
      <span v-html="item.text"></span>
    </li>
  </ul>
</template>

<script setup lang="ts">
const props = defineProps<{
  items: {
    date: string;
    text: string;
  }[];
}>();
</script>

<style scoped>
.news-list {
  margin: 0.3em 0;
  padding-left: 20px;
}

.news-list li {
  margin-bottom: 0.4em;
  line-height: 1.2;
}

.news-date {
  font-weight: 500;
}
</style>
