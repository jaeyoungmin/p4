<template>
  <div class="main-banner">
    <v-img :src="bgImg" min-height="485px">
      <div class="main-banner" no-gutters>
        <h1>
          <span class="typed-text">{{ typeValue }}</span>
          <span class="cursor" :class="{ typing: typeStatus }">&nbsp;</span>
        </h1>
      </div>
    </v-img>
  </div>
</template>

<script>
export default {
  name: 'Mainbanner',
  data() {
    return {
      typeValue: '',
      typeStatus: false,
      typeArray: ["Jaeyoung's PORTFOLIO 🤩"],
      typingSpeed: 100,
      erasingSpeed: 100,
      newTextDelay: 2000,
      typeArrayIndex: 0,
      charIndex: 0,
      bgImg:
        'https://dailytravelstories.com/wp-content/uploads/2019/07/Online-Typing-Jobs-Header.jpg',
    };
  },
  methods: {
    typeText() {
      if (this.charIndex < this.typeArray[this.typeArrayIndex].length) {
        if (!this.typeStatus) this.typeStatus = true;
        this.typeValue += this.typeArray[this.typeArrayIndex].charAt(
          this.charIndex
        );
        this.charIndex += 1;
        setTimeout(this.typeText, this.typingSpeed);
      } else {
        this.typeStatus = false;
        setTimeout(this.eraseText, this.newTextDelay);
      }
    },

    // eraseText() {
    //   if (this.charIndex > 0) {
    //     if (!this.typeStatus) this.typeStatus = true;
    //     this.typeValue = this.typeArray[this.typeArrayIndex].substring(
    //       0,
    //       this.charIndex - 1
    //     );
    //     this.charIndex -= 1;
    //     setTimeout(this.eraseText, this.erasingSpeed);
    //   } else {
    //     this.typeStatus = false;
    //     this.typeArrayIndex += 1;
    //     if (this.typeArrayIndex >= this.typeArray.length)
    //       this.typeArrayIndex = 0;
    //     setTimeout(this.typeText, this.typingSpeed + 1000);
    //   }
    // },
  },
  created() {
    setTimeout(this.typeText, this.newTextDelay + 200);
  },
};
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Xanh+Mono&display=swap');

.main-banner {
  width: 100%;
  height: 100vh;
  background: #00000002;
  display: flex;
  justify-content: center;
  align-items: center;
  a {
    text-decoration: none;
  }
}
h1 {
  font-size: 6rem;
  color: #fff;
  font-weight: 300;

  span.typed-text {
    color: #fff;
    font-size: 6rem;
  }
  span.cursor {
    display: inline-block;
    margin: 0 10px;
    width: 2px;
    border: 0;
    height: 6rem;
    background-color: #fff;
    animation: cursorBlink 1s infinite;
  }
  span.cursor.typing {
    animation: none;
  }
}
@keyframes cursorBlink {
  49% {
    background-color: #fff;
  }
  50% {
    background-color: transparent;
  }
  99% {
    background-color: transparent;
  }
}
</style>
