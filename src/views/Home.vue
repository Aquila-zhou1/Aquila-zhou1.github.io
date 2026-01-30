<!-- src/views/Home.vue -->
<template>
  <div>
    <NavBar :logo-text="logoText" :links="navLinks" />

    <main class="main-container">
      <ProfileHeader
        name="Wenbin Li, PhD"
        title="Associate Professor"
        photo-src="/figs/lwb.jpg"
      />

      <Section id="bio" title="Biography">
        <p style="text-align:justify;">
          I am currently a Tenure-Track Associate Professor of
          <a href="https://is.nju.edu.cn/main.htm" target="_blank">
            School of Intelligence Science and Technology
          </a>
          at
          <a href="http://www.nju.edu.cn/" target="_blank">
            Nanjing University
          </a>
          and a member of
          <a href="https://cs.nju.edu.cn/rl/" target="_blank">
            Reasoning and Learning Research Group
          </a>, led by Prof.
          <a href="https://cs.nju.edu.cn/gaoyang" target="_blank">
            Yang Gao
          </a>.
        </p>
      </Section>

      <Section id="news" title="News">
        <NewsList :items="newsItems" />
      </Section>

      <PublicationList
        id="publications"
        title="Selected Journal Publications"
        :note="pubNote"
        :items="journalPubs"
      />

      <PublicationList
        id="conf-papers"
        title="Selected Conference Publications"
        :note="pubNote"
        :items="confPubs"
      />

      <AppFooter />
    </main>
  </div>
</template>

<script setup lang="ts">
import NavBar from '@/components/NavBar.vue';
import ProfileHeader from '@/components/ProfileHeader.vue';
import Section from '@/components/Section.vue';
import NewsList from '@/components/NewsList.vue';
import PublicationList from '@/components/PublicationList.vue';
import AppFooter from '@/components/AppFooter.vue';

const logoText = 'Wenbin Li';

const navLinks = [
  { id: 'bio', label: 'Biography' },
  { id: 'news', label: 'News' },
  { id: 'publications', label: 'Publications' },
  { id: 'conf-papers', label: 'Conferences' },
];

const newsItems = [
  {
    date: '05/2024',
    text: 'One paper on “dataset distillation” is accepted to <a href="https://cvpr.thecvf.com/" target="_blank">CVPR 2024</a>.',
  },
  {
    date: '05/2024',
    text: '<a href="https://github.com/RL-VIG/LibContinual.git" target="_blank">A comprehensive library for continual learning: LibContinual</a> is released.',
  },
  {
    date: '02/2024',
    text: 'One paper on “dataset distillation” is accepted to <a href="https://cvpr.thecvf.com/" target="_blank">CVPR 2024</a>.',
  },
];

const pubNote =
  '(<sup style="font-size: 12px;">#</sup> indicates equal contribution, ' +
  '<sup style="font-size: 12px;">*</sup> indicates corresponding authorship)';

const journalPubs = [
  {
    title: 'LibFewShot: A Comprehensive Library for Few-shot Learning',
    link: 'https://arxiv.org/abs/2109.04898',
    authors:
      '<strong>Wenbin Li</strong>, Ziyi Wang, Xuesong Yang, Chuanqi Dong, Pinzhuo Tian, Tiexin Qin, Jing Huo, Yinghuan Shi, Lei Wang, Yang Gao and Jiebo Luo.',
    venue:
      'IEEE Transactions on Pattern Analysis and Machine Intelligence (<strong>TPAMI</strong>), 2023. (IF = 18.6)',
    buttons: [
      { label: 'PDF', href: 'https://arxiv.org/abs/2109.04898' },
      { label: 'Code', href: 'https://github.com/RL-VIG/LibFewShot.git' },
      { label: 'arXiv', href: 'https://arxiv.org/abs/2109.04898' },
    ],
  },
  {
    title: 'Defensive Few-shot Learning',
    link: 'https://ieeexplore.ieee.org/document/9916072',
    authors:
      '<strong>Wenbin Li</strong>, Lei Wang, Xingxing Zhang, Lei Qi, Jing Huo, Yang Gao, Jiebo Luo.',
    venue:
      'IEEE Transactions on Pattern Analysis and Machine Intelligence (<strong>TPAMI</strong>), 2023. (IF = 18.6)',
    buttons: [
      { label: 'PDF', href: 'https://ieeexplore.ieee.org/document/9916072' },
      { label: 'Code', href: 'https://github.com/WenbinLee/DefensiveFSL.git' },
    ],
  },
];

const confPubs = [
  {
    title:
      'Exploiting Inter-sample and Inter-feature Relations in Dataset Distillation',
    link:
      'https://openaccess.thecvf.com/content/CVPR2024/html/Deng_Exploiting_Inter-sample_and_Inter-feature_Relations_in_Dataset_Distillation_CVPR_2024_paper.html',
    authors:
      'Wenxiao Deng, <strong>Wenbin Li</strong><sup style="font-size: 12px;">*</sup>, Tianyu Ding, Lei Wang, Hongguang Zhang, Kuihua Huang, Jing Huo, and Yang Gao.',
    venue:
      'Computer Vision and Pattern Recognition (<strong>CVPR</strong>), 2024. (AC Rate = 23.6%)',
    buttons: [
      {
        label: 'PDF',
        href:
          'https://openaccess.thecvf.com/content/CVPR2024/html/Deng_Exploiting_Inter-sample_and_Inter-feature_Relations_in_Dataset_Distillation_CVPR_2024_paper.html',
      },
      { label: 'Code', href: 'https://github.com/VincenDen/IID' },
      { label: 'arXiv', href: 'https://arxiv.org/abs/2404.00563' },
    ],
  },
  {
    title:
      'Modeling Inter-Class and Intra-Class Constraints in Novel Class Discovery',
    link:
      'https://openaccess.thecvf.com/content/CVPR2023/papers/Li_Modeling_Inter-Class_and_Intra-Class_Constraints_in_Novel_Class_Discovery_CVPR_2023_paper.pdf',
    authors:
      '<strong>Wenbin Li</strong>, Zhichen Fan, Jing Huo, Yang Gao.',
    venue:
      'IEEE Conference on Computer Vision and Pattern Recognition (<strong>CVPR</strong>), 2023. (AC Rate = 25.8%)',
    buttons: [
      {
        label: 'PDF',
        href:
          'https://openaccess.thecvf.com/content/CVPR2023/papers/Li_Modeling_Inter-Class_and_Intra-Class_Constraints_in_Novel_Class_Discovery_CVPR_2023_paper.pdf',
      },
      {
        label: 'Code',
        href: 'https://github.com/FanZhichen/NCD-IIC.git',
      },
    ],
  },
];
</script>

<style scoped>
.main-container {
  max-width: 960px;
  margin: 25px auto 40px;
  padding: 0 20px;
}
</style>
