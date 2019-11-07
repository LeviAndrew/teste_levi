<template>
  <v-container>
    {{ msg }}
    <v-btn class="ml-5" @click="back">back</v-btn>
  </v-container>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
  props: ['msg'],
  data: () => ({}),
  methods: {
    ...mapMutations('user', ['BACK_API_REQUIRED']),
    back() {
      this['BACK_API_REQUIRED'](this.api)
      this.$router.replace('/')
    },
  },
}
</script>
