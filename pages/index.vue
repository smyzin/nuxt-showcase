<template>
    <section class="container">
        <div class="container__block" v-if="list && list.length">
            <card v-for="item in list" :key="item.id" :card_data="item"></card>
        </div>
        <pagination :total="max_page" :current_page="current_page" />
    </section>
</template>

<script>
    export default {
        async asyncData(ctx) {
            let max_page = 3,
                page = ctx.route.query.page ? (
                    ctx.route.query.page > max_page ? max_page : ctx.route.query.page
                ) : 1,
                limit = 4,
                skip = page === 1 ? (page - 1) * 4 : (page - 1) * 4 + 1,
                list = await ctx.$axios.get(`https://jsonplaceholder.typicode.com/posts/?_start=${skip}&_limit=${limit}`).then(result => {
                    return result.data;
                }).catch(error => {
                    console.error({error});
                    throw new Error({status: 500, message: 'Что-то пошло не так!'})
                });
            return {
                current_page: page,
                max_page: max_page,
                list: list
            }
        },
        data(){
            return{
            }
        },
        components: {
            'card': require('../components/section/card').default,
            'pagination': require('../components/section/pagination').default,
        },
        watch: {
            $route({query}){
                if(query.page !== this.current_page){
                    this.current_page = query.page;
                    this.getData()
                }
            }
        },
        methods: {
            getData(){
                let page = this.current_page ? (
                        this.current_page > this.max_page ? this.max_page : this.current_page
                    ) : 1,
                    limit = 4,
                    skip = page === 1 ? (page - 1) * 4 : (page - 1) * 4 + 1;
                return this.$axios.get(`https://jsonplaceholder.typicode.com/posts/?_start=${skip}&_limit=${limit}`).then(result => {
                    this.list = result.data;
                }).catch(error => {
                    console.error({error});
                    throw new Error({status: 500, message: 'Что-то пошло не так!'})
                });
            }
        }
    }
</script>

<style>
    /**/
</style>

