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
            console.log( queryData )
        },
        mounted(){
            $( 'a' ).on( 'click', evt => {

                evt.preventDefault()

                // Get json from other page
                $.ajax( {
                    url: evt.target.href,
                    contentType: 'application/json'
                } )
                .done( res => {
                    console.log( res )
                } )
                .fail( xhr => {
                    console.log( 'error', xhr )
                } )
            } )
        }
    }
</script>
