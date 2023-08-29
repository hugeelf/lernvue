<template>
    <div>
        <section class="articles">
            <div class="center articles__die">
                <h2 class="articles__title title_medium">
                    Articles & News
                </h2>
                <ul class="articles__breadcrumbs">
                    <li class="articles__breadcrumb post__description"><a href="index.html">Home</a></li>
                    <li class="articles__breadcrumb post__description"><a href="blog.html">Blog</a></li>
                </ul>
            </div>
        </section>
    </div>
</template>

<script>
export default {
    name: 'ArticlesHeader',

    data() {
        return {

        };
    },

    mounted() {

    },

    methods: {

    },
};
</script>

<style scoped lang="scss">
    .articles {
    padding-top: 180px;
    background-image: url(../assets/img/articles_bg.jpg);
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    display: flex;
    flex-direction: column;
    align-items: center;

    &__die {
        background-color: $colorWhite;
        border-radius: 37px 37px 0px 0px;
        padding: 41px 78px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    &__breadcrumbs {
        display: flex;
        flex-direction: row;

        & li:nth-child(odd)::after {
            content: '/';
            padding-left: 8px;
            padding-right: 8px;
        }
    }

    &__breadcrumb {
        margin-bottom: 0 !important;
    }

    }
</style>