<template>
    <img class="my-2 mx-1 border border-black" :src="src" alt="">
</template>

<script>
export default {
    props: {
        src: {
            type: String,
            default: null,
        }
    }
}
</script>