<template>
  <v-app>
    <router-view></router-view>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  components: {},

  data: () => ({
    //
  }),
};
</script>
<style lang="scss">
.divider {
  width: 56px;
  height: 5px;
  border-top: 1px solid gray;
  border-bottom: 1px solid gray;
  opacity: 0.5;
}
</style>
