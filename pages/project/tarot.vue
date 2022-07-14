<template lang="pug">
  #tarot
    #banner.flex-column.middle-center
      p.title TAROT PROJECT
      p タロットプロジェックト / 塔羅牌企劃
    #content.p-5
      #tab-buttons.flex-row.middle-center
        .btn.button.text-center.py-2.mr-3 GAME
        .btn.button.text-center.py-2 ARTISTS

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
#tarot
  min-height: 100vh
  #banner
    background-color: #CBA1F5
    color: #FFFFFF
    height: 300px
    .title
      font-size: 2.5em
      margin: 50px 0 .25em
  #content
    color: #5D5D5D
    #tab-buttons
      .button
        font-size: 2em
        color: #5D5D5D
        border: #5D5D5D solid 3px
        width: 250px
        border-radius: 25px
        &:hover
          background-color: #5D5D5D
          color: #FFFFFF
</style>
