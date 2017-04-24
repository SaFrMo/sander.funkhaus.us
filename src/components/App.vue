<template>
    <div class="main">

        <component v-for="(q, index) in query" :is="`${q.state}-template`" :key="index">
        </component>

    </div>
</template>

<script>
    /* global queryData */
    // import replaceSVGs from 'replaceSVGs'
    import $ from 'jquery'
    import frontPage from './templates/front-page.vue'

    export default {
        el: '#app',
        components: {
            'front-page-template': frontPage
        },
        data(){
            return {
                query: queryData
            }
        },
        created(){
        },
        mounted(){
    
            // $( 'a' ).on( 'click', evt => {
            //
            //     evt.preventDefault()
            //
            //     // Get json from other page
            //     $.ajax( {
            //         url: evt.target.href,
            //         contentType: 'application/json'
            //     } )
            //     .done( res => {
            //         console.log( res )
            //     } )
            //     .fail( xhr => {
            //         console.log( 'error', xhr )
            //     } )
            // } )
        }
    }
</script>
