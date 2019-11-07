<template>
  <v-app>
    <v-app-bar clipped-left app fixed color="darker">
      <v-toolbar-title class="headline text-uppercase">
        <span>Labtic</span>
      </v-toolbar-title>
      <v-divider class="mx-1" inset vertical />
      <v-toolbar-title class="headline text-uppercase">
        <span class="font-weight-light">API Doc</span>
      </v-toolbar-title>
      <v-spacer />
    </v-app-bar>
    <v-content>
      <router-view />
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  components: {},
  data: () => ({
    //
  }),
}
</script>
