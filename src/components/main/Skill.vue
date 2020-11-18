<template>
  <v-container class="skill d-flex flex-column" ref="portfolio">
    <div class="skill-title">
      <h1 style="text-align:center;font-size:3rem;">#SKILL</h1>
    </div>
    <div class="container" style="max-width:1200px;">
      <v-row>
        <v-col v-for="(skill, i) in skills" :key="i" cols="12" md="4" xs="12">
          <transition name="slide-fade">
            <MySkill
              :title="skill.title"
              :img="skill.imgUrl"
              :text="skill.text"
              v-show="i < timing"
            />
          </transition>
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script>
import { mapState } from 'vuex';
export default {
  name: 'Skill',
  data() {
    return {
      isAppear: false,
      timing: 0,
    };
  },
  computed: {
    ...mapState(['skills']),
  },
  methods: {
    showCard(scrollTop) {
      console.log(this.isAppear);
      console.log(this.timing);
      if (this.$refs.portfolio.offsetTop < scrollTop + 500 && !this.isAppear) {
        this.isAppear = true;
        let interval = setInterval(() => {
          if (this.timing > this.skills.length) {
            clearInterval(interval);
          }
          this.timing++;
        }, 200);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.skill {
  height: 60vh;
}
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(140px);
  opacity: 0;
}
</style>
