<template>
  <v-container
    class="skill d-flex flex-column justify-center pa-3 my-5 "
    ref="skill"
  >
    <h1 style="color:#272727;font-size:3rem;">
      SKILL
      <span style="font-size:3rem;" v-show="isShow">😎</span>
    </h1>
    <div class="divider mt-2"></div>
    <v-row no-gutters>
      <v-col class="wrapper d-flex flex-column px-2" cols="12">
        <MySkill
          v-for="(skill, i) in skills"
          :key="i"
          :title="skill.title"
          :value="i < timing ? skill.value : 0"
          class="skill-item"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { mapState } from 'vuex';
export default {
  name: 'Skill',
  data() {
    return {
      isShow: false,
      timing: 0,
      value: 0,
    };
  },
  components: {
    MySkill: () => import('@/components/main/MySkill.vue'),
  },
  computed: {
    ...mapState(['skills']),
  },
  methods: {
    showSkill(scrollTop) {
      if (this.$refs.skill.offsetTop < scrollTop + 200) {
        this.isShow = true;
      }
    },
    changeValue(scrollTop) {
      if (this.$refs.skill.offsetTop < scrollTop + 400 && !this.isValue) {
        let interval = setInterval(() => {
          if (this.timing > this.skills.length) {
            clearInterval(interval);
          }
          this.timing++;
        }, 1000);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.skill {
  min-height: 700px;
}

.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(250px);
  opacity: 0;
}
</style>
