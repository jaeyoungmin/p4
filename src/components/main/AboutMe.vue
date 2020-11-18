<template>
  <div
    class="about-me pa-0 pa-0 mt-3"
    style="z-index:1;background-color:#fff; position:relative;"
    ref="show"
  >
    <div
      class="about-banner"
      :style="{
        position: isFix ? 'fixed' : undefined,
        left: 'calc(' + 50 + '%' + ' - ' + 250 + 'px)',
        top: 65 + 'px',
      }"
    >
      <v-row class="about-me-item justify-center flex-column" no-gutters>
        <div class="item-title d-flex justify-center">
          <h1 style="font-size:3rem; color:#272727;">
            ABOUT ME
          </h1>
        </div>
        <div class="about-me-text d-flex align-center justify-center">
          <transition name="slide-fade">
            <v-card v-show="scrolled" width="500" min-height="500">
              <p ref="portfolio">{{ introduceText }}</p>
            </v-card>
          </transition>
        </div>
      </v-row>
    </div>
  </div>
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
    positionFix(scrollTop) {
      console.log(this.Fix);
      if (this.$refs.show.offsetTop < scrollTop) {
        this.isFix = true;
      } else {
        this.isFix = undefined;
      }

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
    },
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
        '집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다 에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다',
      scrolled: false,
      isFix: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.about-me {
  z-index: 2;
  min-height: 100vh;
  position: relative;
  width: 100%;
}
.slide-fade-enter-active {
  transition: all 0.5s ease;
}
.slide-fade-leave-active {
  transition: all 0.5s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateY(400px);
  opacity: 0;
}
</style>
