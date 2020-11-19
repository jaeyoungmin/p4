<template>
  <v-container
    fluid
    class="features d-flex align-center flex-column pa-3"
    ref="portfolio"
  >
    <div class="feature-banner" style="max-width:1200px;margin:0 auto;">
      <div class="features-title">
        <v-col>
          <h1 style="font-size:3rem; color:#272727">
            FEATURE <span v-show="isShow"> 🙋‍♂</span>
          </h1></v-col
        >
      </div>
      <div class="divider mx-3"></div>
      <div class="container">
        <v-row>
          <v-col v-for="(feature, i) in features" :key="i" cols="12" lg="4">
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
  </v-container>
</template>

<script>
import { mapState } from 'vuex';
export default {
  name: 'Features',
  data() {
    return {
      isAppear: false,
      timing: 0,
      isShow: false,
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
    showImg(scrollTop) {
      if (this.$refs.portfolio.offsetTop < scrollTop + 200) {
        this.isShow = true;
      }
    },
    // showFix(scrollTop) {
    //   if (this.$refs.portfolio.offsetTop < scrollTop + 80) {
    //     this.isFix = true;
    //   } else {
    //     this.isFix = undefined;
    //   }
    // },
  },
};
</script>

<style lang="scss" scoped>
.features {
  background: #f5deb3;
  min-height: 800px;
}
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateY(340px);
  opacity: 0;
}
</style>
