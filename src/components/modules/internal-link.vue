<template>

    <a :href="href" @click="loadQueryData" :class="classes">
        <slot></slot>
    </a>

</template>

<script>
/* global $ */

export default {
    name: 'internal-link',
    props: {
        href: {
            type: String,
            default: '#'
        },
        class: {
            type: [Array, Object, String],
            default: 'internal-link'
        }
    },
    computed: {
        classes(){ return this.class }
    },
    methods: {
        loadQueryData(){
            $.ajax( {
                url: this.href,
                contentType: 'application/json',
                dataType: 'json',
                success: ( data ) => {
                    this.$root.query = data
                },
                error: err => console.log( 'error', err )
            } )
        }
    }
}

</script>
