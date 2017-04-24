<template>

    <section class="front-page" v-html="query.post_content">
        {{ query }}
    </section>

</template>

<script>

export default {
    data(){
        return {
        }
    },
    computed: {
        query(){
            return this.$root.query.data[0]
        }
    }
}

</script>

<style>

</style>
