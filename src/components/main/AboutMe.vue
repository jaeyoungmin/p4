<template>
  <v-container class="about-me pa-0 pa-0 mt-13" ref="show">
    <v-row class="about-me-item justify-center flex-column" no-gutters>
      <div class="item-title d-flex justify-center">
        <h1 style="font-size:4rem;">
          ABOUT ME
        </h1>
      </div>
      <div class="about-me-text d-flex align-center justify-center">
        <v-scale-transition>
          <v-card
            flat
            v-show="scrolled"
            width="300"
            min-height="500"
            ref="portfolio"
          >
            <p>{{ introduceText }}</p>
          </v-card>
        </v-scale-transition>
      </div>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'AboutMe',
  methods: {
    showText(scrollTop) {
      console.log(this.scrolled);
      if (this.$refs.show.offsetTop < scrollTop) {
        this.scrolled = true;
        console.log('YES');
      }
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
        '집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다집에가고싶다',
      scrolled: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.about-me {
  height: 80vh;
}
</style>
