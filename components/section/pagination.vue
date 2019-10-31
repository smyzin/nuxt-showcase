<template>
    <div class="pagination">
        <button class="pagination__btn" :class="parseInt(current_page) === num ? 'pagination__btn_active' : ''" v-for="num in total" :key="num"
            @click="$router.push(`/?page=${num}`)"
        >
            <span>
                {{ num }}
            </span>
        </button>
        <button class="pagination__btn" @click="current_page < total ?$router.push(`/?page=${parseInt(current_page) + 1}`) : ''"
            :class="parseInt(current_page) === total ? 'pagination__btn_active' : ''"
        >
            <span>
                Следующая
            </span>
        </button>
        <button class="pagination__btn" @click="current_page < total ? $router.push(`/?page=${total}`) : ''"
                :class="parseInt(current_page) === total ? 'pagination__btn_active' : ''"
        >
            <span>
                Последняя
            </span>
        </button>
    </div>
</template>

<script>
    export default {
        props: {
            total: {
                type: Number,
                default: 3
            },
            current_page: {
                type: String,
                default: '1'
            }
        }
    }
</script>

<style scoped>

</style>
