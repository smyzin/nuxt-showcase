<template>
    <footer class="footer">
        <div class="footer__nav">
            <div class="footer__nav-block">
                <h2 class="footer__nav-block-title">О сервисе</h2>
                <nav class="footer__nav-block-menu">
                    <nuxt-link class="footer__nav-block-menu-item" active-class="footer__nav-block-menu-item_active" to="/">Заказчикам</nuxt-link>
                    <nuxt-link class="footer__nav-block-menu-item" active-class="footer__nav-block-menu-item_active" to="/1">Исполнителям</nuxt-link>
                    <nuxt-link class="footer__nav-block-menu-item" active-class="footer__nav-block-menu-item_active" to="/2">Самозанятым</nuxt-link>

                    <nuxt-link class="footer__nav-block-menu-item" active-class="footer__nav-block-menu-item_active" to="/3">Партнерская программа</nuxt-link>
                    <nuxt-link class="footer__nav-block-menu-item" active-class="footer__nav-block-menu-item_active" to="/4">Реклама на сайте</nuxt-link>
                    <nuxt-link class="footer__nav-block-menu-item" active-class="footer__nav-block-menu-item_active" to="/4">Помощь</nuxt-link>
                </nav>
            </div>
            <div class="footer__nav-block">
                <h2 class="footer__nav-block-title">О нас</h2>
                <nav class="footer__nav-block-menu">
                    <nuxt-link class="footer__nav-block-menu-item" active-class="footer__nav-block-menu-item_active" to="/">История компании</nuxt-link>
                    <nuxt-link class="footer__nav-block-menu-item" active-class="footer__nav-block-menu-item_active" to="/1">Реквизиты</nuxt-link>
                    <nuxt-link class="footer__nav-block-menu-item" active-class="footer__nav-block-menu-item_active" to="/2">Частным лицам</nuxt-link>

                    <nuxt-link class="footer__nav-block-menu-item" active-class="footer__nav-block-menu-item_active" to="/3">Партнерская программа</nuxt-link>
                    <nuxt-link class="footer__nav-block-menu-item" active-class="footer__nav-block-menu-item_active" to="/4">Реклама на сайте</nuxt-link>
                    <nuxt-link class="footer__nav-block-menu-item" active-class="footer__nav-block-menu-item_active" to="/4">Помощь</nuxt-link>
                </nav>
            </div>
        </div>
        <small class="footer__copyright">
            &copy; 2018 Компания
        </small>

    </footer>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>

</style>
