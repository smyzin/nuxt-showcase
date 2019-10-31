<template>
    <div class="wrap">
        <app-header/>
        <main>
            <nuxt/>
        </main>
        <app-footer/>
    </div>
</template>
<script>
    // import TopHeader from '../components/layout/header'

    export default {
        components: {
            'app-header': require('../components/layout/header').default,
            'app-footer': require('../components/layout/footer').default,

        }
    }
</script>

<style>
    html {
        /*font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;*/
        /*font-size: 16px;*/
        /*word-spacing: 1px;*/
         /*-ms-text-size-adjust: 100%;*/
         /*-webkit-text-size-adjust: 100%;*/
         /*-moz-osx-font-smoothing: grayscale;*/
         /*-webkit-font-smoothing: antialiased;*/
        /*box-sizing: border-box;*/
    }
    .wrap{
        padding: 41px 115px 64px 115px;
    }
    @import '../assets/scss/main.scss';
</style>
