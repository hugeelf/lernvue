<template>
    <footer class="center footer">
        <div class="footer__company">
            <a href="./index.html" class="header__logo-link footer__header">
                <img src="../assets/img/logo.svg" alt="logo" class="logo__img" />
                <span>{{ siteName }}</span>
            </a>
            <p class="post__description footer__info">It is a long established fact that a reader will be distracted
                lookings.</p>
            <div class="footer__social">
                <ul class="footer__social-links">
                    <li class="footer__link" v-for="socialLink in socialLinks" :key="socialLink.id">
                        <a :href="socialLink.address"><img :src="socialLink.img" alt="social link"></a>
                    </li>
                </ul>
            </div>
        </div>
        <div class="footer__links-wrapper">
            <p class="news-preview__title footer__title">Pages</p>
            <ul class="header__links footer__links">
                <li class="header__link" v-for="link in links" :key="link.id">
                    <a :href="link.address" class="header__link">{{ link.name }}</a>
                </li>
            </ul>
        </div>
        <div class="footer__contacts">
            <p class="news-preview__title footer__title">Contact</p>
            <a href="https://goo.gl/maps/Vq5nBg7oARGYqGN66" class="header__link contacts__address">55 East Birchwood Ave.
                Brooklyn, New York 11201</a>
            <a href="mailto:contact@interno.com" class="header__link contacts__address">contact@interno.com</a>
            <a href="tel:+1234567890" class="header__link contacts__address">(123) 456 - 7890</a>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'SiteFooter',

    data() {
        return {
            logoLink: "./img/logo.svg",
            siteName: "Interno",
            links: [
                { id: 1, name: "Home", address: "./index.html" },
                { id: 2, name: "Projects", address: "#" },
                { id: 3, name: "Blog", address: "#" },
            ],
            socialLinks: [
                { id: 1, name: 'twitter', address: 'www.twitter.com', img: './img/twitter.svg' },
                { id: 2, name: 'linkedIn', address: 'www.linkedin.com', img: './img/linkedin.svg' },
            ],
        };
    },

    mounted() {

    },

    methods: {

    },
};
</script>

<style lang="scss">
.footer {
    &__header {
        margin-bottom: 18px;
    }

    display: grid;
    grid-template-columns: repeat(3, 1fr);

    &__info {
        margin-bottom: 31px;
    }

    &__social-links {
        display: flex;
        flex-direction: row;
        gap: 54px;

    }

    &__title {
        margin-bottom: 35px;
    }

    &__links {
        flex-direction: column;
        align-items: flex-start;

        &-wrapper {
            padding-left: 95px;
        }
    }

    &__contacts {
        display: flex;
        flex-direction: column;
        padding-left: 143px;

        &>a,
        &>p {
            text-align: left;
        }

        & a:nth-child(n+2) {
            padding-bottom: 40px;
        }
    }
}
</style>