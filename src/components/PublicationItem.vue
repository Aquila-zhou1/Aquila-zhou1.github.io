<!-- src/components/PublicationItem.vue -->
<template>
  <li class="pub-item">
    <a :href="link" target="_blank">{{ title }}</a><br />
    <span class="spacer"></span>
    <span class="authors" v-html="authors"></span><br />
    <span class="venue" v-html="venue"></span><br />
    <div class="buttons" v-if="buttons && buttons.length">
      <a v-for="btn in buttons"
         :key="btn.label"
         class="button button4"
         :href="btn.href"
         target="_blank">
        {{ btn.label }}
      </a>
    </div>
  </li>
</template>

<script setup lang="ts">
const props = defineProps<{
  title: string;
  link: string;
  authors: string;       // 用 HTML 字符串，方便加粗作者名
  venue: string;         // 包含期刊名、年份、IF 等
  buttons?: {
    label: string;
    href: string;
  }[];
}>();
</script>

<style scoped>
.pub-item {
  padding: 8px;
  margin-bottom: 8px;
  border-radius: 5px;
  border-bottom: 1px dotted #eaeaea;
  transition: all 0.2s ease;
}

.pub-item a:first-of-type {
  font-weight: 500;
  color: #2a4a8c;
  text-decoration: none;
  transition: color 0.3s;
}

.pub-item a:first-of-type:hover {
  color: #3498db;
  text-decoration: underline;
}

.spacer {
  display: block;
  height: 5px;
}

.venue {
  color: #e74c3c;
}

.button {
  font-family: Georgia, serif;
  background-color: #d6eaf8;
  border: none;
  color: #022b6d;
  padding: 4px 8px;
  text-decoration: none;
  display: inline-block;
  font-size: 0.85em;
  margin: 2px 3px;
  border-radius: 4px;
  transition: all 0.3s ease;
}

.button:hover {
  background-color: #aed6f1;
  transform: translateY(-2px);
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

/* hover card 效果 */
.pub-item:hover {
  background-color: #f5f5f5;
  border-left: 5px solid #4285f4;
  box-shadow: 0 5px 15px rgba(66, 133, 244, 0.2);
  transform: translateX(5px);
  padding-left: 10px;
}
</style>
