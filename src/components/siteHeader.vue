<template>
    <nav class="header center">
        <a href="./index.html" class="header__logo-link">
            <img src="../assets/img/logo.svg" alt="logo" class="logo__img" />
            <span>{{ siteName }}</span>
        </a>
        <ul class="header__links">
            <li class="header__link" v-for="link in links" :key="link.id">
                <a :href="link.address" class="header__link">{{ link.name }}</a>
            </li>
        </ul>
    </nav>
</template>

<script>
export default {
    name: 'SiteHeader',

    data() {
        return {
            logoLink: './assets/img/logo.svg',
            siteName: "Interno",
            links: [
                { id: 1, name: "Home", address: "./index.html" },
                { id: 2, name: "Projects", address: "#" },
                { id: 3, name: "Blog", address: "#" },
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
.header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 52px 0px;

    &__logo-link {
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 12px;
        color: $colorBlackText;
        font-family: $fontFamilyDM;
        font-size: 40px;
        font-style: normal;
        font-weight: 400;
        line-height: 125%;
        /* 50px */
    }

    &__links {
        display: flex;
        flex-direction: row;
        gap: 40px;
    }

    &__link {
        color: $colorBlackText;
        text-align: center;
        font-family: $fontFamilyJost;
        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: 125%;
        /* 25px */
    }
}
</style>