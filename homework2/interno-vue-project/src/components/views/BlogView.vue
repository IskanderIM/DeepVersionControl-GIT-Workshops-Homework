<template>
  <div>
    <div class="container">
      <div class="blogpage__banner">
        <div class="blogpage__banner-into">
          <h1 class="blogpage__banner-intoHead">
            Статьи & Новости
          </h1>
          <div class="blogpage__banner-breadcrumbs">
            Домой / Блог
          </div>
        </div>
      </div>
    </div>
    <div class="container">
      <div class="blogpage">
        <div class="blogpage__latestPost">
          <div class="blogpage__heading-title">
            Последний пост
          </div>
          <div class="blogpage__latestPost-card">
            <div class="blogpage__latestPost-post">
              <div class="blogpage__latestPost-img" />
              <div class="blogpage__latestPost-content">
                <div class="blogpage__latestPost-subcontent">
                  <div class="blogpage__latestPost-title">
                    Low Cost Latest Invented Interior Designing Ideas
                  </div>
                  <div class="blogpage__latestPost-text">
                    С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов. Перед появлением электронных издательств дизайнеры импровизировали в работе над макетами, изображая текст при помощи волнистых линий. С появлением самоклеющихся наклеек с напечатанным текстом «Lorem ipsum» появился более реалистичный способ обозначения расположения текста на странице.
                  </div>
                </div>
                <div class="blogpage__latestPost-date">
                  <div class="blogpage__latestPost-date_text">
                    26 December,2022
                  </div>
                  <router-link
                    to="/blog-details"
                    class="project__contnet_block-link"
                  >
                    <svg
                      width="52"
                      height="53"
                      viewBox="0 0 52 53"
                      fill="none"
                      xmlns="http://www.w3.org/2000/svg"
                    >
                      <circle
                        class="blog__blog_subcontent"
                        cx="26"
                        cy="26.2671"
                        r="26"
                        fill="#F4F0EC"
                      />
                      <path
                        d="M23.7715 32.9529L29.7144 26.2672L23.7715 19.5815"
                        stroke="#292F36"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      />
                    </svg>
                  </router-link>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="blogpage__artcle-and-news">
        <div class="blog blogpage__blog">
          <div class="blog__heading">
            <div class="blog__heading-title">
              Статьи & Новости
            </div>
          </div>
          <div
            class="blog__blog"
            id="artandnews"
          >
            <ArtAndNews />
            <!-- <BlogDetails /> -->
          </div>
        </div>
        <div class="blogpage__pagination">
          <div class="blogpage__pagination-page">
            01
          </div>
          <div class="blogpage__pagination-page">
            02
          </div>
          <div class="blogpage__pagination-page">
            03
          </div>
          <div class="blogpage__pagination-page">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="53"
              height="52"
              viewBox="0 0 53 52"
              fill="none"
            >
              <circle
                cx="26.5"
                cy="26"
                r="25.5"
                stroke="none"
              />
              <path
                d="M23.5571 32L29.5 25.3143L23.5571 18.6286"
                stroke="#292F36"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import BlogDetails from '@/components/blocks/BlogDetails.vue'
import ArtAndNews from '../blocks/ArtAndNews.vue'
export default {
  name: 'BlogView',
  components: {
    ArtAndNews
    // BlogDetails
  },
  data () {
    return {
    }
  },

  mounted () {

  },

  methods: {

  }
}
</script>

<style lang="scss" scoped>

</style>
