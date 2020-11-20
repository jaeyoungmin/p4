<template>
  <div class="story-slider">
    <div class="wrapper">
      <div class="story-item" v-for="(story, i) in stories" :key="i">
        <img :src="story.img" alt="#" contain />
        <p>{{ story.name }}</p>
      </div>
      <!-- /.story-item -->
    </div>
    <!-- /.wrapper -->
  </div>
</template>

<script>
import { mapState } from 'vuex';
export default {
  name: 'StorySlider',
  computed: { ...mapState(['stories', 'myProfile']) },
  //변경안함
};
</script>

<style lang="scss" scoped>
.story-slider {
  overflow-x: auto;
  background-color: #fafafa;
}
.wrapper {
  max-width: 1200px;
  margin: 20px auto;
  padding: 10px 10px 0;
  white-space: nowrap;
}
.story-item {
  display: inline-block;
  margin-right: 5%;
  text-align: center;
  img {
    max-width: 300px;
    height: 300px;
    object-fit: cover;
    vertical-align: middle;
  }
  p {
    font-size: 12px;
  }
}
</style>
