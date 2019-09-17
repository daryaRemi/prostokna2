<template lang="pug">
    #test Test Page
        Footer
</template>

<style lang="scss">
    #test {
        background: #000;
        width: 300px;
        height: 300px;
        color: #ffffff;
    }
</style>

<script>
import Footer from '~/components/Footer/component.vue'
export default {
  components: {
    Footer
  }
}
</script>
