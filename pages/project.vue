<template lang="pug">
  #project
    #navbar.pt-5.pb-4
      .flex-row.middle-center
        NuxtLink.nav-button.px-4(to="/") HOME
        NuxtLink.nav-button.px-4(to="/project/tarot") TAROT
        NuxtLink.nav-button.px-4(to="/project/video") VIDEO
        NuxtLink.nav-button.px-4(to="/project/comment") COMMENT
        NuxtLink.nav-button.px-4(to="/project/staff") STAFF
        .flex-fill
        #profile-pic.px-4
          img(src="~assets/images/profile.png")
    NuxtChild
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
#project
  background-color: #F1FFFF
  #navbar
    color: #737373
    &>div
      height: 120px
      .nav-button
        text-decoration: none
        color: inherit
        font-size: 1.5em
        font-weight: 500
        &::first-letter
          font-size: 1.5em
      #profile-pic
        img
          width: 120px
  #footer
    background-color: #122D42
    min-height: 100px
</style>
