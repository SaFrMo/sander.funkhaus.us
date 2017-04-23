<template>
    <div class="main" v-html="query.data[0].post_content">

        <span v-if="!query">Error loading!</span>

    </div>
</template>

<script>
    /* global queryData */
    // import replaceSVGs from 'replaceSVGs'
    import $ from 'jquery'

    export default {
        el: '#app',
        data(){
            return {
                query: queryData
            }
        },
        created(){
            console.log( $( 'a' ) )
            console.log( queryData )
        },
        mounted(){
            $( 'a' ).on( 'click', evt => {
                evt.preventDefault()
            } )
        }
    }
</script>
