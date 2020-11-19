<template>
  <v-container
    class="about-me d-flex justify-center align-center pa-3 "
    ref="show"
  >
    <v-row justify="center" no-gutters>
      <v-col cols="12" lg="6" md="5">
        <h1 style="font-size:3rem; color:#272727;">
          ABOUT ME <span v-show="isShow">🙇‍♂</span>
        </h1>
        <div class="divider mb-4"></div>
        <div class="about-me-text d-flex align-center justify-center">
          <transition name="slide-fade">
            <p class="pa-2" v-show="scrolled">{{ introduceText }}</p>
          </transition>
        </div>
      </v-col>
      <v-col class="mt-4" cols="12" lg="6" md="7">
        <v-scale-transition>
          <v-hover v-slot="{ hover }">
            <v-card :class="{ 'on-hover': hover }" class="ml-2" elevation="0">
              <img
                v-show="isShow"
                :src="iuimg"
                alt="#"
                style="min-width:100px;width:100%;"
              />
            </v-card>
          </v-hover>
        </v-scale-transition>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'AboutMe',
  methods: {
    showText(scrollTop) {
      if (this.$refs.show.offsetTop < scrollTop + 400) {
        this.scrolled = true;
      }
    },
    showImg(scrollTop) {
      if (this.$refs.show.offsetTop < scrollTop + 200) {
        this.isShow = true;
      }
    },

    // positionFix(scrollTop) {
    //   console.log(this.Fix);
    //   if (this.$refs.show.offsetTop < scrollTop + 100) {
    //     this.isFix = true;
    //   } else {
    //     this.isFix = undefined;
    //   }

    // console.log(
    //   this.$refs.show.offsetTop + this.$refs.show.clientHeight + 250
    // );
    // console.log(scrollTop + window.innerHeight);
    // console.log(this.isFix);
    // if (
    //   this.$refs.show.offsetTop + this.$refs.show.clientHeight <
    //   scrollTop + window.innerHeight + 45
    // ) {
    //   this.isFix = true;
    // } else {
    //   this.isFix = undefined;
    // }
    // }
    // scrollCallbackElAppear(scrollTop) {
    //   if (this.$refs.portfolio.offsetTop < scrollTop && !this.isElAppear) {
    //     this.isElAppear = true;
    //     let interval = setInterval(() => {
    //       if (this.timing > 5) {
    //         clearInterval(interval);
    //       }
    //       this.timing++;
    //     }, 200);
    //   }
    // },
  },
  data() {
    return {
      introduceText:
        'Vuetify is the #1 component library for Vue.js and has been in active development since 2016. The goal of the project is to provide users with everything that is needed to build rich and engaging web applications using the Material Design specification. It accomplishes that with a consistent update cycle, Long-term Support (LTS) for previous versions, responsive community engagement, a vast ecosystem of resources and a dedication to quality components.',
      scrolled: false,
      scrolled1: false,
      isShow: false,
      isShow1: false,
      iuimg:
        'https://6.vikiplatform.com/image/a11230e2d98d4a73825a4c10c8c6feb0.jpg?x=b&a=0x0&s=590x330&q=h&e=t&f=t&cb=1',
    };
  },
};
</script>

<style lang="scss" scoped>
.about-me {
  z-index: 2;
  position: relative;
  width: 100%;
  min-height: 800px;
}
.v-card {
  transition: opacity 0.4s ease-in-out;
}
.v-card:not(.on-hover) {
  opacity: 0.6;
}
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.5s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(-800px);
  opacity: 0;
}
</style>
