<!-- src/views/Detail.vue -->
<template>
  <div>
    <NavBar :logo-text="logoText" :links="[]" />
    <main class="main-container">
      <h1>Detail Page (Wenbin-style full homepage)</h1>
      <p>
        这里以后你可以放完整的 Wenbin Li 样式主页（包括全部 Publications / Teaching / Services / Mentoring 等）。
      </p>
    </main>
  </div>
</template>

<script setup lang="ts">
import NavBar from '@/components/NavBar.vue';

const logoText = 'Wenbin Li';
</script>

<style scoped>
.main-container {
  max-width: 960px;
  margin: 25px auto 40px;
  padding: 0 20px;
}
</style>
