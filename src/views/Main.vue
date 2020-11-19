<template>
  <div class="main">
    <MainBanner />
    <div class="main-wrap">
      <AboutMe ref="aboutEl" />
      <Skill ref="skillEl" />
    </div>
    <Parallax />
    <Features ref="featuresEl" />
    <Contact />
  </div>
</template>

<script>
export default {
  name: 'Main',
  mounted() {
    document.addEventListener('scroll', () => {
      this.$refs.aboutEl.showText(window.scrollY);
      this.$refs.aboutEl.showImg(window.scrollY);
      // this.$refs.aboutEl.positionFix(window.scrollY);

      this.$refs.skillEl.showSkill(window.scrollY);
      this.$refs.skillEl.changeValue(window.scrollY);
      this.$refs.featuresEl.showCard(window.scrollY);
      this.$refs.featuresEl.showImg(window.scrollY);
      // this.$refs.featuresEl.showFix(window.scrollY);
    });
  },
  components: {
    MainBanner: () => import('@/components/main/MainBanner.vue'),
    AboutMe: () => import('@/components/main/AboutMe.vue'),
    Parallax: () => import('@/components/main/Parallax.vue'),
    Skill: () => import('@/components/main/Skill.vue'),
    Features: () => import('@/components/main/Features.vue'),
    Contact: () => import('@/components/main/Contact.vue'),
  },
};
</script>

<style lang="scss" scoped>
.main {
  min-width: 375px;
}
.main-wrap {
  max-width: 1200px;
  margin: 0 auto;
}
</style>
