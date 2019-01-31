<template>
  <div id="app">
    <router-view/>
    <FooterGuide v-show="$route.meta.showFooter"/>
  </div>
</template>

<script>
import { mapActions } from 'vuex'
import FooterGuide from './components/FooterGuide/FooterGuide.vue'
// import { reqFoodCategorys } from './api'

export default {
  mounted() {
    //this.$store.dispatch('getAddress')
    this.getAddress()
  },

  methods: {
    //显示数据要两种状态:更新状态(下面)和读状态(MSite.vue)
    ...mapActions(['getAddress'])
  },
  components: {
    FooterGuide
  },
}
</script>

<style lang="stylus" rel="stylesheep/stylus">
.app {
  width: 100%;
  height: 100%;
  background: #f5f5f5;
}
</style>

