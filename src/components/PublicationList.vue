<!-- src/components/PublicationList.vue -->
<template>
  <Section :id="id" :title="title">
    <p v-if="note" class="note" v-html="note"></p>
    <ol class="pub-list">
      <PublicationItem
        v-for="pub in items"
        :key="pub.title"
        v-bind="pub"
      />
    </ol>
  </Section>
</template>

<script setup lang="ts">
import Section from './Section.vue';
import PublicationItem from './PublicationItem.vue';

interface PubButton {
  label: string;
  href: string;
}

interface PubItem {
  title: string;
  link: string;
  authors: string;
  venue: string;
  buttons?: PubButton[];
}

const props = defineProps<{
  id: string;
  title: string;
  note?: string;
  items: PubItem[];
}>();
</script>

<style scoped>
.pub-list {
  margin-top: 0.3em;
  padding-left: 20px;
}
.note {
  font-size: 0.85em;
  color: #555;
}
</style>
