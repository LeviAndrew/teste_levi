<template>
  <v-container>
    {{ test }}
    <v-col cols="12" md="6" sm="4">
      <v-text-field
        v-model="api.name"
        :rules="regrateste"
        :counter="20"
        label="Name"
        equired
      ></v-text-field>
    </v-col>

    <v-col cols="12" md="6" sm="4">
      <v-textarea v-model="api.description" color="black" label="Description"></v-textarea>
    </v-col>

    <v-col cols="12" md="6" sm="4">
      <v-text-field
        v-model="api.path"
        :rules="regrateste"
        :counter="10"
        label="path"
        required
      ></v-text-field>
    </v-col>

    <v-col cols="12" md="6" sm="4">
      <v-select
        v-model="api.method"
        :items="methods"
        :rules="regrateste"
        label="Method"
        required
      ></v-select>
    </v-col>
    <v-btn class="ml-5" :disabled="test" @click="prox">next</v-btn>
  </v-container>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
  data: () => ({
    api: {
      name: '',
      description: '',
      path: '/',
      method: '',
    },
    regrateste: [(v) => !!v || 'Item is required'],
    methods: ['GET', 'PUT', 'POST', 'DELETE'],
  }),
  computed: {
    test() {
      return !this.api.name || !this.api.description || !this.api.method || this.api.path.length < 2
    },
  },
  methods: {
    ...mapMutations('user', ['SET_API_REQUIRED']),
    prox() {
      this['SET_API_REQUIRED'](this.api)
      this.$router.push('/pagetwo')
    },
  },
}
</script>
