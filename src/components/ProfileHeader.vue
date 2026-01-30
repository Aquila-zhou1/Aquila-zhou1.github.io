<!-- src/components/ProfileHeader.vue -->
<template>
  <section class="profile-container">
    <div class="profile-info">
      <h1>{{ name }}</h1>
      <h3>{{ title }}</h3>
      <p>
        <a href="https://keysoftlab.nju.edu.cn/" target="_blank">
          State Key Laboratory for Novel Software Technology
        </a><br />
        <a href="https://is.nju.edu.cn/main.htm" target="_blank">
          School of Intelligence Science and Technology
        </a><br />
        <a href="https://cs.nju.edu.cn/rl/index_eng.htm" target="_blank">
          Reasoning and Learning Research Group
        </a><br />
        <a href="http://www.nju.edu.cn/" target="_blank">
          Nanjing University, Suzhou Campus, China
        </a><br /><br />
        Email:
        <a href="mailto:liwenbin@nju.edu.cn">liwenbin@nju.edu.cn</a>;
        <a href="mailto:liwenbin.nju@gmail.com">liwenbin.nju@gmail.com</a>
        <br /><br />
        <span class="social-links">
          <a class="social-link"
             href="https://scholar.google.com/citations?user=K-kC4yYAAAAJ&hl=zh-CN&authuser=1"
             target="_blank">Google Scholar</a>
          |
          <a class="social-link" href="https://github.com/WenbinLee" target="_blank">GitHub</a>
          |
          <a class="social-link" href="https://github.com/RL-VIG" target="_blank">GitHub-VIG</a>
        </span>
      </p>
    </div>

    <div class="profile-image">
      <img :src="photoSrc" :alt="name" class="profile-photo" />
    </div>
  </section>
</template>

<script setup lang="ts">
const props = defineProps<{
  name: string;
  title: string;
  photoSrc: string;
}>();
</script>

<style scoped>
.profile-container {
  display: flex;
  align-items: center;
  gap: 30px;
  margin-bottom: 1.5em;
}

.profile-info {
  flex: 2;
}

.profile-image {
  flex: 1;
  text-align: center;
}

.profile-photo {
  max-width: 270px;
  border-radius: 5px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  transition: transform 0.3s ease;
}

.profile-photo:hover {
  transform: scale(1.03);
}

.social-links {
  margin-top: 10px;
}

.social-link {
  color: #527bbd;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s;
}

.social-link:hover {
  color: #2a4a8c;
  border-bottom: 1px solid;
}

@media (max-width: 768px) {
  .profile-container {
    flex-direction: column-reverse;
    text-align: center;
  }
}
</style>
