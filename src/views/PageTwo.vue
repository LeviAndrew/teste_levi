<template>
  <div class="pagetwo">
    <comp-two :msg="myMsg" />
    <comp-two :msg="myMsg" />
    <comp-two :msg="myMsg" />
  </div>
</template>

<script>
// @ is an alias to /src
import compTwo from '@/components/CompTwo.vue'

export default {
  name: 'CompTwo',
  components: {
    compTwo,
  },
  data: () => ({
    myMsg: 'Welcome to Your Vue.jsoutrakdhakfjahfkjah khk adhfkaljh',
  }),
}
</script>
