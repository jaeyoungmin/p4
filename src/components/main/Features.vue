<template>
  <div class="features d-flex flex-column" ref="portfolio">
    <div class="features-title">
      <h1 style="text-align:center;font-size:3rem;">FEATURE</h1>
    </div>
    <div class="container" style="max-width:1200px;">
      <v-row>
        <v-col
          v-for="(feature, i) in features"
          :key="i"
          cols="12"
          md="4"
          xs="12"
        >
          <transition name="slide-fade">
            <MyFeature
              :title="feature.title"
              :img="feature.imgUrl"
              :text="feature.text"
              v-show="i < timing"
            />
          </transition>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex';
export default {
  name: 'Features',
  data() {
    return {
      isAppear: false,
      timing: 0,
    };
  },
  components: { MyFeature: () => import('@/components/main/MyFeature.vue') },
  computed: {
    ...mapState(['features']),
  },
  methods: {
    showCard(scrollTop) {
      if (this.$refs.portfolio.offsetTop < scrollTop + 400 && !this.isAppear) {
        this.isAppear = true;
        let interval = setInterval(() => {
          if (this.timing > this.features.length) {
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
.features {
  position: relative;
  z-index: 3;
  height: 100vh;
  background-color: white;
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
