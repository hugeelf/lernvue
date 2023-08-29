<template>
  <div id="app"> 
    <site-header></site-header>
    <div v-if="myTrigger === 'cli-hw'">
      <button @click="triggerer('articles')" class="temp-button">Задание со списком статей</button>
      <articles-header></articles-header>
      <big-post></big-post>
      <news></news>
    </div>
    <div v-else-if="myTrigger === 'articles'">
      <button @click="triggerer('cli-hw')" class="temp-button">Обратно</button>
      <blog-list></blog-list>
    </div>
    <site-footer></site-footer>
  </div>
</template>

<script>
import siteHeader from './components/siteHeader.vue';
import articlesHeader from './components/articlesHeader.vue';
import bigPost from './components/bigPost.vue';
import news from './components/news.vue';
import siteFooter from './components/siteFooter.vue'
import blogList from './components/blogList.vue'
export default {
  name: 'App',
  data(){
    return{
      myTrigger: 'cli-hw',
    }
  },
  components: {
    'siteHeader': siteHeader,
    'articlesHeader': articlesHeader,
    'bigPost': bigPost,
    'news': news,
    'siteFooter': siteFooter,
    'blogList': blogList,
  },
  methods: {
    triggerer(param){
      this.myTrigger = param;
    }
  },
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=Jost:wght@300;400;500&display=swap');

.button_active {
  border: 1px solid transparent;
  background-color: $colorActive;
}

.title_medium {
  color: $colorBlackText;
  font-family: $fontFamilyDM;
  font-size: 50px;
  font-style: normal;
  font-weight: 400;
  line-height: 125%;
  letter-spacing: 1px;
}
.temp-button{
  background-color: red;
  position: fixed;
  top: 0;
  padding:20px 40px;
  z-index: 1000;
}

// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
//   margin-top: 60px;
// }
</style>
