<template>
    <section class="relative overflow-hidden">
        <img class="hero" :src="activeItem.img" alt="">
        <div class="absolute top-1/2 transform -translate-y-1/2 left-1/2 flex overflow-x-hidden">
            <button class="self-end border border-black mr-1" @click="prevSlide"><img class="max-w-min" src="~/static/images/left.svg" alt="Left"></button>
            <button class="self-end border border-black" @click="nextSlide"><img class="max-w-min" src="~/static/images/right.svg" alt="Right"></button>
            <div class="slides flex">
                <HeroSingleSlide v-for="ref,index in references" :key="ref.key" :src="ref.tmb" :class="{ 'active': index === 0 }" />
            </div>
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
            references: [
                {
                    'key': 1,
                    'img': 'https://via.placeholder.com/1920x1080/255',
                    'tmb': 'https://via.placeholder.com/200x300/255',
                },
                {
                    'key': 2,
                    'img': 'https://via.placeholder.com/1920x1080/600',
                    'tmb': 'https://via.placeholder.com/200x300/600',
                },
                {
                    'key': 3,
                    'img': 'https://via.placeholder.com/1920x1080/002012',
                    'tmb': 'https://via.placeholder.com/200x300/002012',
                },
                {
                    'key': 4,
                    'img': 'https://via.placeholder.com/1920x1080/012304',
                    'tmb': 'https://via.placeholder.com/200x300/012304',
                },
                {
                    'key': 5,
                    'img': 'https://via.placeholder.com/1920x1080/012304',
                    'tmb': 'https://via.placeholder.com/200x300/012304',
                },
                {
                    'key': 6,
                    'img': 'https://via.placeholder.com/1920x1080/1024',
                    'tmb': 'https://via.placeholder.com/200x300/1024',
                }
            ],
            keyActive: 1
        }
    },
    computed: {
        lastItem() {
            return this.references.slice(-1)[0]
        },
        activeItem() {
            return this.references.find( ref => {
                return ref.key === this.keyActive
            })
        }
    },
    methods: {
        prevSlide() {
            const [first, ...rest] = this.references
            this.keyActive = first.key
            this.references = [...rest, first]
        },
        nextSlide() {
            const lastItem = this.lastItem
            this.keyActive = lastItem.key
            this.references.pop()
            this.references = [lastItem, ...this.references]
        }
    },
}
</script>