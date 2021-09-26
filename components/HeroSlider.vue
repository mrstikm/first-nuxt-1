<template>
    <section class="relative overflow-hidden">
        <img class="hero" src="https://via.placeholder.com/1920x1080" alt="">
        <div class="slides absolute top-1/2 transform -translate-y-1/2 left-1/2 flex overflow-x-hidden">
            <HeroSingleSlide v-for="img, index in imgSrcs" :key="index" :src="img" />
        </div>
    </section>
</template>

<script>
import HeroSingleSlide from './HeroSingleSlide.vue'
export default {
    components: {
        HeroSingleSlide
    },
    data() {
        return {
            imgSrcs: [
                'https://via.placeholder.com/200x300',
                'https://via.placeholder.com/200x300',
                'https://via.placeholder.com/200x300',
                'https://via.placeholder.com/200x300',
                'https://via.placeholder.com/200x300',
                'https://via.placeholder.com/200x300',
            ]
        }
    }
}
</script>