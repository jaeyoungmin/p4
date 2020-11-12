<template>
  <div class="home">
    <div class="cursor"></div>

    <CoreAppBar />
    <CoreView />
    <CoreFooter />
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
    CoreAppBar: () => import('@/components/core/CoreAppBar.vue'),
    CoreView: () => import('@/components/core/CoreView.vue'),
    CoreFooter: () => import('@/components/core/CoreFooter.vue'),
  },
  mounted() {
    const cursor = document.querySelector('.cursor');
    document.addEventListener('mousemove', (e) => {
      cursor.setAttribute(
        'style',
        'top: ' + (e.pageY - 10) + 'px; left:' + (e.pageX - 10) + 'px'
      );
    });

    document.addEventListener('click', () => {
      cursor.classList.add('expand');

      setTimeout(() => {
        cursor.classList.remove('expand');
      }, 500);
    });
  },
};
</script>
<style lang="scss">
* {
  margin: 0;
  padding: 0;
  font-family: consolas;
  box-sizing: border-box;
  cursor: none;
}
.home {
  min-height: 100vh;
  background-color: #050801;
}
.cursor {
  width: 20px;
  height: 20px;
  border: 1px solid white;
  border-radius: 50%;
  position: absolute;
  transition-duration: 200ms;
  transition-timing-function: ease out;
  animation: cursorAnim 0.5s infinite alternate;
}

.expand {
  animation: cursorAnim3 0.5s forwards;
  border: 1px solid#03e9f4;
}

@keyframes cursorAnim {
  from {
    transform: scale(1);
  }

  to {
    transform: scale(0.7);
  }
}

@keyframes cursorAnim3 {
  0% {
    transform: scale(1);
  }

  50% {
    transform: scale(2);
  }

  100% {
    tranform: scale(1);
  }
}
</style>
