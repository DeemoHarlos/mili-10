<template lang="pug">
  #index
    #content.position-relative(ref="bgRef" :style="{ height: bgHeight + 'px' }")
      .moon(v-for="moonCss in moonsCss" :style="moonCss")
    #footer
</template>

<script lang="ts">
import { computed, defineComponent, onMounted, ref } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const bgRef = ref<(HTMLElement) | null>(null)

    const moonSize = 0.203
    const moonLeft = 0.187 - moonSize / 2
    const moonRight = 0.197 - moonSize / 2
    const bgWidth = ref(1920)
    const bgHeight = computed(() => bgWidth.value * 2.59)
    const moonSizeCss = computed(() => (
      { width:  moonSize * bgWidth.value + 'px', height: moonSize * bgWidth.value + 'px' }
    ))
    const moonsCss = computed(() => [
      { left:  moonLeft  * bgWidth.value + 'px', top: 0.843 * bgWidth.value + 'px', ...moonSizeCss.value },
      { right: moonRight * bgWidth.value + 'px', top: 1.253 * bgWidth.value + 'px', ...moonSizeCss.value },
      { left:  moonLeft  * bgWidth.value + 'px', top: 1.614 * bgWidth.value + 'px', ...moonSizeCss.value },
      { right: moonRight * bgWidth.value + 'px', top: 1.968 * bgWidth.value + 'px', ...moonSizeCss.value },
      { left:  moonLeft  * bgWidth.value + 'px', top: 2.310 * bgWidth.value + 'px', ...moonSizeCss.value },
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
      bgHeight,
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
  background: no-repeat top/100% url('~assets/images/bg2.png')
  .moon
    background-color: #EEF09B
    position: absolute
    border-radius: 50%
#footer
  background-color: #85BDF7
  height: 10vw
</style>
