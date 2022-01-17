<script>
import BlogCard from './components/BlogCard.vue'

export default {
  components: {
    BlogCard
  },

  data() {
    return {
      name: 'Weekly Roundup',
      category: 'NFT',
      image: 'https://academy-public.coinmarketcap.com/optimized-uploads/b4a1f7607ba046ca8f96acc1e3ebd122.jpg',
      author: 'Mathieu de Gouville',
      desc: `Steph Curry Purchases LinksDAO NFT, Pushes Price to New Highs`,
      link: 'https://coinmarketcap.com/alexandria/article/weekly-roundup-what-happened-in-play2earn-games-and-nfts-this-week-jan-14-2022'
    }
  },

  methods: {
    async fetchData() {
      // NOTE: 1/2 API Request should look like this
      // const { name, category, image, author, desc, link } = await axios.get(`https://api.com/articles/last`)

      // NOTE: 2/2 but we're using a mock API
      const { name, category, image, author, desc, link } = {
        name: 'Weekly Roundup',
        category: 'NFT',
        image: 'https://academy-public.coinmarketcap.com/optimized-uploads/b4a1f7607ba046ca8f96acc1e3ebd122.jpg',
        author: 'Mathieu de Gouville',
        desc: `Steph Curry Purchases LinksDAO NFT, Pushes Price to New Highs`,
        link: 'https://coinmarketcap.com/alexandria/article/weekly-roundup-what-happened-in-play2earn-games-and-nfts-this-week-jan-14-2022'
      }

      this.name = name
      this.category = category
      this.image = image
      this.author = author
      this.desc = desc
      this.link = link
    }
  },

  created() {
    this.fetchData()
  }
}
</script>

<template lang="pug">
#container
  blog-card(
    :name="name"
    :category="category"
    :image="image"
    :author="author"
    :desc="desc"
    :link="link"
  )
</template>

<style lang="stylus">
@import url("https://fonts.googleapis.com/css?family=Lato:400,700")
*
  box-sizing: border-box

  &::before, 
  &::after
    box-sizing: border-box

body
  margin 0
  padding 0

  #app
    display flex
    font-family "Lato", sans-serif
    font-weight 400
    color #777
    background #ccd8ee
    font-size .9rem
    min-height 100vh
    margin 0
    line-height 1.6
    align-items center
    justify-content center
    text-rendering optimizeLegibility

    #container
      width 30rem
      height 13.625rem
</style>
