<template lang="pug">
  #index
    #content.position-relative(ref="bgRef")
      .moon(v-for="moonCss in moonsCss" :style="moonCss")
    #footer
</template>

<script lang="ts">
import { computed, defineComponent, onMounted, ref } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const bgRef = ref<(HTMLElement) | null>(null)

    const moonSize = 0.2
    const moonLeft = 0.187 - moonSize / 2
    const moonRight = 0.197 - moonSize / 2
    const bgWidth = ref(1920)
    const moonSizeCss = computed(() => (
      { width:  moonSize * bgWidth.value + 'px', height: moonSize * bgWidth.value + 'px' }
    ))
    const moonsCss = computed(() => [
      { left:  moonLeft  * bgWidth.value + 'px', top: 0.843 * bgWidth.value + 'px', ...moonSizeCss },
      { right: moonRight * bgWidth.value + 'px', top: 1.253 * bgWidth.value + 'px', ...moonSizeCss },
      { left:  moonLeft  * bgWidth.value + 'px', top: 1.614 * bgWidth.value + 'px', ...moonSizeCss },
      { right: moonRight * bgWidth.value + 'px', top: 1.968 * bgWidth.value + 'px', ...moonSizeCss },
      { left:  moonLeft  * bgWidth.value + 'px', top: 2.310 * bgWidth.value + 'px', ...moonSizeCss },
    ])

    onMounted(() => {
      bgWidth.value = bgRef.value?.clientWidth || 1920
      window.onresize = () => {
        bgWidth.value = bgRef.value?.clientWidth || 1920
      }
    })

    return {
      bgRef,
      bgWidth,
      moonsCss,
    }
  },
})
</script>

<style lang="sass" scoped>
$moon-size: 20vw
$moon-left: calc(18.6vw - #{$moon-size} / 2)
$moon-right: calc(20vw - #{$moon-size} / 2)

#content
  width: 100%
  height: 259vw
  background: no-repeat top/100% url('~assets/images/bg2.png')
  .moon
    background-color: #EEF09B
    position: absolute
    width: $moon-size
    height: $moon-size
    border-radius: 50%
    &:nth-child(1)
      left: $moon-left
      top: 83.1vw
    &:nth-child(2)
      right: $moon-right
      top: 123.8vw
    &:nth-child(3)
      left: $moon-left
      top: 159.5vw
    &:nth-child(4)
      right: $moon-right
      top: 194.4vw
    &:nth-child(5)
      left: $moon-left
      top: 228vw
#footer
  background-color: #85BDF7
  height: 10vw
</style>
