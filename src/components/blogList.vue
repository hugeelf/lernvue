<!-- blogs-list (компонент который выводит список из компонент blog и фильтрует его на основе выбранного тега) -->
<template>
    <div class="blog-lists center">
        <blog-detail :blogsList="blogsList"></blog-detail>
        <div>
            <div>
                <button v-for="(category, index) in categories" :key="index" @click="filterBlog(category)">{{ category }}</button>
            </div>
            <blog :filteredBlogList="filteredBlogList"></blog>
        </div>
    </div>
</template>

<script>
import blog from './blog.vue'
import blogDetail from './blogDetail.vue'
export default {
    name: 'VueProjectBlogList',

    data() {
        return {
            blogsList: [
                {
                    blogId: 0, blogHeader: 'Let’s Get Solution for BuildingConstruction Work', blogDate: '26 December,2022', blogMainText: `Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don't look even slightly believable.
                    Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary.`, blogTags: ['Kitchen', 'Kitchen Planning'], blogImg:['blog_main.jpg', 'blog_second.jpg'], blogQuote:'The details are not the details. They make the design.'
                },
                {
                    blogId: 1, blogHeader: 'Let’s Get Solution for BuildingConstruction Work 2', blogDate: '27 December,2022', blogMainText: `Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don't look even slightly believable.
                    Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary.2`, blogTags: ['Bedroom', 'Architecture'], blogImg:['blog_second.jpg', 'blog_main.jpg' ], blogQuote:'The details are not the details. They make the design.'
                },
                {
                    blogId: 2, blogHeader: 'Let’s Get Solution for BuildingConstruction Work 3', blogDate: '28 December,2022', blogMainText: `Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don't look even slightly believable.
                    Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary.3`, blogTags: ['Building', 'Architecture'], blogImg:['blog_main.jpg', 'blog_second.jpg'], blogQuote:'The details are not the details. They make the design.'
                },
            ],
            categories: ['Kitchen', 'Bedroom', 'Building', 'Architecture', 'Kitchen Planning'],
            howToFilter: 'Building',
            currentBlog: 0,
        };
    },
    components: {
        blog,
        blogDetail,
    },
    mounted() {

    },

    methods: {
        filterBlog(filterNmae){
            this.howToFilter = filterNmae;
        },
    },
    computed: {
        filteredBlogList() {
            return this.blogsList.filter(item => item.blogTags.includes(this.howToFilter))
        },
    }
};
</script>

<style lang="scss" scoped>
    .blog-lists{
        display: grid;
        grid-template-columns: 2fr 1fr;
    }
</style>