<template>
  <div class="my-feature">
    <v-img :src="img" height="300" alt="img"></v-img>
    <h3>{{ title }}</h3>
    <p>{{ text }}</p>
    <v-btn>NEXT</v-btn>
  </div>
</template>

<script>
export default {
  name: 'MyFeature',
  props: ['title', 'img', 'text'],
  data() {
    return {
      isElAppear: false,
      timeing: 0,
    };
  },
};
</script>

<style lang="scss" scoped></style>
