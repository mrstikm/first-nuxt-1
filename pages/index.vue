<template>
  <div class="h-screen">
    <Header />
    <main>
      <HeroSlider />
    </main>
  </div>
</template>

<script>
import Header from '~/components/Header.vue'
import HeroSlider from '~/components/HeroSlider.vue'

export default {
  components: {
    Header,
    HeroSlider
  }
}
</script>