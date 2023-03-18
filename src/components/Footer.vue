<template>
      <v-footer
        color="orange"
        dark
      >
        <v-row
          justify="center"
          class="my-0 text-center"
        >
          <strong>Contact us</strong>
          <v-col cols="12">
            <v-btn
              v-for="icon in icons"
              :key="icon"
              text
              dark
            >
              <v-icon>{{ icon }}</v-icon>
            </v-btn>
          </v-col>
          <v-col
            cols="12"
            class="align-center"
            ><strong> &copy; {{ new Date().getFullYear() }}-Silas.Service.com</strong></v-col
          >
        </v-row>
      </v-footer>
  </template>
<script>
export default {
  name: 'Footer',
  data: () => {
    return {
      icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-instagram',
        'mdi-youtube',
      ],
    };
  },
};
</script>