<template>
    <header class="header">
        <div class="header__logo">
            Компания
        </div>
        <nav class="header__menu">
            <nuxt-link class="header__menu-item" active-class="header__menu-item_active" exact to="/">Проекты</nuxt-link>
            <nuxt-link class="header__menu-item" active-class="header__menu-item_active" to="/tasks">Задачи</nuxt-link>
            <nuxt-link class="header__menu-item" active-class="header__menu-item_active" to="/news">Новости</nuxt-link>
            <nuxt-link class="header__menu-item" active-class="header__menu-item_active" to="/vacancy">Вакансии</nuxt-link>
            <nuxt-link class="header__menu-item" active-class="header__menu-item_active" to="/contacts">Контакты</nuxt-link>
        </nav>
    </header>
</template>

<script>
    export default {
        name: 'TopHeader'
    }
</script>

<style lang="scss">

</style>
