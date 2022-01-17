<script>
export default {
  props: {
    name: String,
    category: String,
    image: String,
    author: String,
    desc: String,
    link: String,
  }
}
</script>

<template lang="pug">
a.card-link(:href="link")
  article.blog-card 
    img.post-image(:src="image")
    .article-details 
      h4.post-category {{ category }}
      h3.post-title {{ name }}
      p.post-description {{ desc }}
      p.post-author By {{ author }}
</template>

<style lang="stylus" scoped>
.card-link
  position relative
  display block
  color inherit
  text-decoration none

  &:hover
    .post-title
      transition color 0.3s ease
      color #e04f62

  &:hover
    .post-image
      transition opacity 0.3s ease
      opacity 0.9

.blog-card
  display flex
  flex-direction row
  background #fff
  box-shadow 0 0.1875rem 1.5rem rgba(0, 0, 0, 0.2)
  border-radius 0.375rem
  overflow hidden

.post-image
  transition opacity 0.3s ease
  display block
  width 100%
  object-fit cover

.article-details
  padding 1.5rem

.post-category
  display inline-block
  text-transform uppercase
  font-size 0.75rem
  font-weight 700
  line-height 1
  letter-spacing 0.0625rem
  margin 0 0 0.75rem 0
  padding 0 0 0.25rem 0
  border-bottom 0.125rem solid #ebebeb

.post-title
  transition color 0.3s ease
  font-size 1.125rem
  line-height 1.4
  color #121212
  font-weight 700
  margin 0 0 0.5rem 0

.post-author
  font-size 0.875rem
  line-height 1
  margin 1.125rem 0 0 0
  padding 1.125rem 0 0 0
  border-top 0.0625rem solid #ebebeb

@media(max-width 40rem)
  #container
    width 18rem
    height 27.25rem
  
  .blog-card
    flex-wrap wrap
  
@supports(display grid)
  #app
    display grid
    grid-template-columns repeat(4, 1fr)
    grid-gap 0.625rem
    grid-template-areas ". main main ." ". main main ."
  
  #container
    grid-area main
    align-self center
    justify-self center

  .post-image
    height 100%

  .blog-card
    display grid
    grid-template-columns 1fr 2fr
    grid-template-rows 1fr

  @media (max-width 40rem)
    .blog-card
      grid-template-columns auto
      grid-template-rows 12rem 1fr
</style>
