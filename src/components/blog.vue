<template>
    <div class="blog-list__preview">
        <ul>
            <li v-for="blog in filteredBlogList" :key="blog.blogId">
                <h2>{{ blog.blogHeader }}</h2>
                <p>{{ blog.blogDate }}</p>
                <p>{{ blog.blogMainText.substring(0, 50) }} ...</p>
                <button @click="showBlogById(blog.blogId)">Подробнее</button>
                <br>
            </li>
        </ul>
    </div>
</template>

<script>

import {bus} from '../main';

export default {
    name: 'VueProjectBlog',
    props:['filteredBlogList'],
    data() {
        return {
            data: 1,
        };
    },

    mounted() {
        
    },

    methods: {
        showBlogById(blogId){
            this.data = blogId;   
            bus.$emit('selectBlog', this.data)
        }
    },
};
</script>

<style lang="scss" scoped>

</style>