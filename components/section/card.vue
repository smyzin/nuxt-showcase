<template>
    <div class="card">
        <div class="card__header">
            <div class="card__header-title" @click="$router.push(`/${card_data.id !== null ? card_data.id : '/'}`)">
                {{ card_data.title }}
            </div>
            <div class="card__header-chevron" @click="card_opened = !card_opened">
                <i class="fa" :class="card_opened ? 'fa-chevron-up' : 'fa-chevron-down'"></i>
            </div>
        </div>
        <div class="card__body" v-if="card_opened">
            {{ card_data.body }}
        </div>
        <div class="card__date">
            22.06.2018 в 16:44, изменена 23.06.2018 в 11:10
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            card_data: {
                require: true,
                type: Object,
                default: () => {
                    return {
                        title: 'Не указан',
                        body: 'Тут ничего нет',
                        id: null
                    }
                }
            }
        },
        data(){
            return{
                card_opened: false,
            }
        }
    }
</script>

<style scoped>

</style>
