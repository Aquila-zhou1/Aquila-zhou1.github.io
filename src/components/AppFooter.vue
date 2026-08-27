<!-- src/components/AppFooter.vue -->
<template>
  <footer class="footer">
    <div class="footer-content">
      <p>&copy; 2026 Martin Tianyuan Zhou | <em>Last update: Aug. 2026</em></p>
    </div>
    <div ref="mapRef"></div>
  </footer>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
const mapRef = ref<HTMLElement | null>(null)
onMounted(() => {
  const script = document.createElement('script')
  script.type="text/javascript"
  script.id="mapmyvisitors"
  script.src = 'https://mapmyvisitors.com/map.js?cl=ffffff&w=300&t=tt&d=z1bI_cN485kRPddZxhqxky3xLs9gyF6rlTjRLx-qil4'
  mapRef.value?.appendChild(script)
})
</script>

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
