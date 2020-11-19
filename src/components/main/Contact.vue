<template>
  <v-container fluid class="contact-me d-flex flex-column justify-center">
    <h1 style="font-size:3rem;color:#f5deb3">
      {{ 'Contact Me'.toUpperCase() }}
    </h1>
    <div class="divider"></div>
    <!-- /.divider -->
    <v-row class="form flex-column justify-center" style="max-width:1200px;">
      <v-col>
        <v-text-field
          placeholder="Name*"
          color="white"
          solo
          v-model="name"
        ></v-text-field>
        <v-text-field
          placeholder="Email*"
          color="white"
          solo
          v-model="email"
        ></v-text-field>
        <v-text-field
          placeholder="Subject*"
          color="white"
          solo
          v-model="subject"
        ></v-text-field>
        <v-textarea solo placeholder="Message*" v-model="message"></v-textarea>
      </v-col>
      <v-btn color="#f5deb3" @click="requestSendEmail">Submit</v-btn>
    </v-row>
    <!-- /.form -->
    <!-- <div v-for="(bodys, i) in body.data" :key="i">
      <h3>
        {{ 'Name :' + bodys.employee_name }}
        {{ 'Age :' + bodys.employee_age }}
      </h3>
    </div> -->
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
</style>
