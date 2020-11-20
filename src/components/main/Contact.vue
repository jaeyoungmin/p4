<template>
  <v-container fluid class="contact-me pa-3">
    <div class="contact-text">
      <h1>Contact</h1>
    </div>
    <div class="contact-form">
      <v-text-field
        color="white"
        dense
        placeholder="Message*"
        solo
      ></v-text-field>
      <v-text-field
        color="white"
        dense
        placeholder="Email*"
        solo
      ></v-text-field>
      <v-text-field
        color="white"
        dense
        placeholder="Subject*"
        solo
      ></v-text-field>
      <v-textarea color="white" placeholder="Message*" solo></v-textarea>
    </div>
  </v-container>
</template>

<script>
export default {
  name: 'Contact',
};
</script>

<style lang="scss" scoped>
.contact-me {
  background: #272727;
}
.contact-text {
  max-width: 1200px;
  margin: 0 auto;
  h1 {
    font-size: 3rem;
    color: #f5deb3;
  }
}
.contact-form {
  max-width: 1200px;
  margin: 0 auto;
}
</style>
