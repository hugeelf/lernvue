<template>
    <section class="post center">
        <h2 class="post__title title_medium">Latest Post</h2>
        <div class="post__element">
            <img src="../assets/img/post_1.jpg" alt="post image" class="post__img">
            <div class="post__text">
                <h4 class="post__title">
                    {{ post.title }}
                </h4>
                <p class="post__description">
                    {{ post.shortDescription }}
                </p>
                <p class="post__thing">
                    {{ post.mainThing }}
                </p>
                <div class="news-preview__wrap">
                    <p class="news-preview__date">{{ post.date }}</p>
                    <button class="button_main">
                        <svg width="9" height="16" viewBox="0 0 9 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M1.27101 14.9525L7.21387 8.26683L1.27101 1.58112" stroke="#292F36" stroke-width="2"
                                stroke-linecap="round" stroke-linejoin="round" />
                        </svg>
                    </button>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'BigPost',

    data() {
        return {
            post: {
                id: 1,
                title: "Low Cost Latest Invented Interior Designing Ideas",
                shortDescription:
                    "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpis dignissim maximus.posuere in.Contrary to popular belief.",
                mainThing:
                    "Lorem Ipsum is not simply random text. It has roots in a piece of classica.",
                date: "26 December,2022 ",
            },
        };
    },

    mounted() {

    },

    methods: {

    },
};
</script>

<style lang="scss">
.post {
    padding-top: 200px;

    &__title {
        padding-bottom: 0;
    }

    &__element {
        display: flex;
        flex-direction: row;
        gap: 65px;
        margin-bottom: 150px;
        border-radius: 62px;
        border: 1px solid #E7E7E7;
        box-shadow: 0px 10px 30px 0px rgba(255, 255, 255, 0.25);
        padding: 22px;
    }

    &__img {
        border-radius: 62px;
    }

    &__text {
        padding: 50px 34px 51px 0px;
    }

    &__title {
        color: $colorBlackText;
        font-family: $fontFamilyDM;
        font-size: 25px;
        font-style: normal;
        font-weight: 400;
        line-height: 125%;
        letter-spacing: 0.5px;
        max-width: 460px;
        margin-bottom: 22px;
    }

    &__description,
    &__thing {
        color: $colorBlackText;
        font-family: $fontFamilyJost;
        font-size: 22px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%;
        letter-spacing: 0.22px;
        margin-bottom: 41px;
        max-width: 469px;
    }
}
</style>