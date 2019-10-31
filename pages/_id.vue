<template>
    <div class="page">
        <article class="page__post">
            <h1 class="page__post-title">{{ post.title }}</h1>
            <div class="page__post-body">
                {{ post.body }}
            </div>
        </article>
        <section class="page__comments">
            <h2 class="page__comments-title">Комментарии</h2>

            <comment-card v-for="comment in comments" :key="comment.id" :card_data="comment" ></comment-card>

            <button class="page__comments-refresh" @click="getNewComments">
                <i class="fa fa-refresh"></i>
                <span>Показать еще</span>
            </button>
        </section>
    </div>
</template>

<script>
    export default {
        async asyncData(ctx) {
            let id = ctx.route.params.id,
                limit = 3,
                skip = 0,
                comments = await ctx.$axios.get(`https://jsonplaceholder.typicode.com/posts/${id}/comments?_start=${skip}&_limit=${limit}`).then(result => {
                    return result.data;
                }).catch(error => {
                    console.error({error});
                    throw new Error({status: 500, message: 'Что-то пошло не так!'})
                }),
                post = await ctx.$axios.get(`https://jsonplaceholder.typicode.com/posts/${id}`).then(result => {
                    return result.data;
                }).catch(error => {
                    console.error({error});
                    throw new Error({status: 500, message: 'Что-то пошло не так!'})
                });

            return {
                id: id,
                post: post,
                skip: skip,
                comments: comments
            }
        },
        components: {
            'comment-card': require('../components/section/commentCard').default,
        },
        methods: {
            getNewComments(){
                this.skip = this.skip + 3;
                this.$axios.get(`https://jsonplaceholder.typicode.com/posts/${this.id}/comments?_start=${this.skip}&_limit=${3}`).then(result => {
                    this.comments.push(...result.data);
                }).catch(error => {
                    console.error({error});
                    throw new Error({status: 500, message: 'Что-то пошло не так!'})
                });
            }
        }
    }
</script>

<style scoped>

</style>
