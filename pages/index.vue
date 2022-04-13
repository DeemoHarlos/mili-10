<template lang="pug">
  #index.text-white.flex-column
    #banner.flex-row
      div.flex-fill
      #logo
        img(src="~assets/images/mili-logo.png")
    #navbar.flex-row
      div.normal-button.flex-fill
      div.star-button.flex-fill
      div.star-button.flex-fill
      div.star-button.flex-fill
      div.star-button.flex-fill
      div.normal-button.flex-fill
    #content.flex-fill
    #footer
</template>

<script lang="ts">
import { defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    return {}
  },
})
</script>

<style lang="sass" scoped>
#index
  min-height: 100vh
  // background-color: $mili
  background: no-repeat top/cover url('~assets/images/bg.png')
  #banner
    height: 200px
    #logo
      padding: 2rem
      img
        height: 100%
  #navbar
    height: 80px
    .normal-button
      background: $mili
      &:first-child
        margin-right: 2px
      &:last-child
        margin-left: 2px
    .star-button
      background: no-repeat center/cover url('~assets/images/button-star.png')
      margin: 0 2px
  #content
    background: no-repeat center url('~assets/images/coming-soon.png')
    mix-blend-mode: overlay
    opacity: 90%
  #footer
    height: 60px
    background: #1B3B54
</style>
