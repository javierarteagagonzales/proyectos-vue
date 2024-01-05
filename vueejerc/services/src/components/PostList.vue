<template>
<h1>Listado de posts</h1>
<ul class="post-list">
    <li v-for="post in posts" :key="post.id"> {{ post.title }}</li>
</ul>
</template>

<script lang="ts" setup>
    /* *******composition API javascript
    import { defineComponent, onMounted } from 'vue';
    import PostService from '@/services/PostService'

    export default defineComponent({
        name: 'PostList',
        setup() {
            const service = new PostService()
            const posts = service.getPosts()

            onMounted(async () => {
                await service.fetchAll()
            })
            return{posts}
        }
    })  */

    /* Option API javascript
    import { defineComponent, onMounted } from 'vue';
    import PostService from '@/services/PostService'

    export default defineComponent({
        name: 'PostList',
        data() {
            const service = new PostService()
            const posts = service.getPosts()
            return {posts, service}
        },
        async mounted (){
            await this.service.fetchAll()
        }
    })
    */

    // Composition setup javascript
    import { defineComponent, onMounted } from 'vue';
    import PostService from '@/services/PostService'

    const service = new PostService()
    const posts = service.getPosts()

    onMounted(async () => {
        await service.fetchAll()
    })

</script>

<style scoped lang="scss">
$red: #ff0000;
    .post-list {
        width: 96vw;
        height: 75px;
        padding: 25px;
        list-style-type: none ;
    }

    .post-list li {
        padding: 10px;
        width: 100%;
        border: 1px solid #ccc;
        color: $red;
    }
</style>