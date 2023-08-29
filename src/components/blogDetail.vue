<template>
    <div class="blog-wrapper">
        <div class="blog-current" v-for="blog in currentBlogShow" :key="blog.blogId">
            <h2 class="blog-current__title">{{ blog.blogHeader }}</h2> 
            <img :src="require(`@/assets/img/${blog.blogImg[0]}`)" alt="">
            <p>{{ blog.blogDate }}</p>
            <p>{{ blog.blogMainText }}</p>
            <blockquote> {{ blog.blogQuote }}</blockquote>
            <img :src="require(`@/assets/img/${blog.blogImg[1]}`)" alt="">
        </div>
          
            
    </div>
</template>

<script>
import {bus} from '../main';
export default {
    name: 'VueProjectBlogDetail',
    props: ['blogsList'],
    data() {
        return {
            currentBlog: 0,
            
        };
    },

    created(){
        bus.$on('selectBlog', data=> {
            this.currentBlog=data;
        })
    },

    mounted() {
        
    },

    methods: {
    },
    computed: {
        currentBlogShow(){
            return this.blogsList.filter(item=>item.blogId === this.currentBlog);
        }
    },
};
</script>

<style lang="scss" scoped>

</style>