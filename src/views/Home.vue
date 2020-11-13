<template>
  <div class="home">
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
};
</script>
<style lang="scss">
* {
  margin: 0;
  padding: 0;
  font-family: consolas;
  box-sizing: border-box;
}
.home {
  min-height: 100vh;
  background-color: #050801;
}
</style>
