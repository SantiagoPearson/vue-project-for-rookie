<template>
    <div id="app">
      <router-view/>
      <FooterGuide v-show="$route.meta.showFooter"/>
    </div>
</template>

<script>
  import {mapActions} from 'vuex'
  import FooterGuide from './components/FooterGuide/FooterGuide.vue'
  import { Button } from 'mint-ui';
  import Vue from 'vue'

  Vue.component(Button.name, Button);
    export default {
      mounted () {
        // this.$store.dispatch('getAddress')
        this.getAddress()
        // this.getUserInfo()
        this.$store.dispatch('getUserInfo')
      },

      methods: {
        ...mapActions(['getAddress', 'getUserInfo'])
      },

      components: {
        FooterGuide
      }

    }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .app
    width 100%
    height 100%
    background #f5f5f5

</style>
