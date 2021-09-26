<template>
    <div class="flex items-center">
        <NuxtLogo class="w-40" />
        <Navigation />
    </div>
</template>

<script>
import NuxtLogo from './NuxtLogo.vue'
import Navigation from './Navigation.vue'
export default {
    components: {
        NuxtLogo,
        Navigation
    }
}
</script>