<!-- src/components/AppFooter.vue -->
<template>
  <footer class="footer">
    <div class="footer-content">
      <p>&copy; 2025 Tianyuan Zhou | <em>Last update: Feb. 2026</em></p>
    </div>
    <div class="visitor-map-wrapper">
      <a
        href="https://mapmyvisitors.com/web/1c30d"
        title="Visit tracker"
        target="_blank"
      >
        <img
          class="visitor-map-img"
          src="https://mapmyvisitors.com/map.png?d=pd9i878wd5hSvDEbYzOxFOA_A08c-cdrBe1NccL-_ys&cl=ffffff&h=320"
          alt="Visitor map"
        />
      </a>
    </div>
  </footer>
</template>

<script setup lang="ts"></script>

<style scoped>
.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 20px;
  padding: 10px 0;
  border-top: 1px solid #eaeaea;
  text-align: center;
  font-size: 0.9em;
  color: #777;
}

.footer-content {
  max-width: 600px;
  margin: 0 auto;
}
</style>
