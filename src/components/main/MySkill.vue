<template>
  <div class="feature-item mt-3">
    <v-row align="center">
      <v-col>
        <h2>
          {{ title }}
        </h2>
      </v-col>
      <v-col>
        <v-progress-linear
          height="20"
          rounded
          :size="100"
          :width="30"
          :value="value"
          color="#f5deb3"
        >
          <span style="color:#272727">{{ value }}%</span>
        </v-progress-linear>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: 'MySkill',
  props: ['title', 'value'],
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
