<template>
  <div id="app">
    <HeaderBlock />

    <router-view />
    <FooterBlock />
  </div>
</template>

<script>
import HeaderBlock from './components/blocks/HeaderBlock.vue'
import FooterBlock from './components/blocks/FooterBlock.vue'

export default {
  name: 'App',
  components: {
    HeaderBlock,
    FooterBlock
  }
}
</script>
<style lang="scss">

// Обнуление стилей
*, *:before, *:after{
  box-sizing: border-box;
}

html, body, div, span, object, iframe, figure, h1, h2, h3, h4, h5, h6, p, blockquote, pre, a, code, em, img, small, strike, strong, sub, sup, tt, b, u, i, ol, ul, li, fieldset, form, label, table, caption, tbody, tfoot, thead, tr, th, td, main, canvas, embed, footer, header, nav, section, video{
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  text-size-adjust: none;
  text-decoration: none;
}

footer, header, nav, section, main{
  display: block;
}

body{
  line-height: 1;
}

ol, ul{
  list-style: none;
}

blockquote, q{
  quotes: none;
}

blockquote:before, blockquote:after, q:before, q:after{
  content: '';
  content: none;
}

table{
  border-collapse: collapse;
  border-spacing: 0;
}

input{
  -webkit-appearance: none;
  border-radius: 0;
}

//  подключение шрифтов
@font-face {
  font-family: 'Font-Awesome-5-Brands-Regular';
  src:
    url('./assets/fonts/Font-Awesome-5-Brands-Regular.ttf.woff') format('woff'),
    url('./assets/fonts/Font-Awesome-5-Brands-Regular.ttf.svg#Font-Awesome-5-Brands-Regular') format('svg'),
    url('./assets/fonts/Font-Awesome-5-Brands-Regular.ttf.eot'),
    url('./assets/fonts/Font-Awesome-5-Brands-Regular.ttf.eot?#iefix') format('embedded-opentype');
  font-weight: normal;
  font-style: normal;
  }

// подключение переменных
body {
}
.container {
  padding-right: 0!important;
  padding-left: 0!important;
  margin: 0 auto;
  width: 1200px;
  background-color: #fff;
  max-width: 1200px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: row;
  margin-top: 50px;
  &__left {
    display:flex;
    &_block-logo {
    display: flex;
    align-content: center;
    align-items: center;
    flex-direction: row;
    gap: 10px;
    }
  };
  &__right {
    display: flex;
  };
  &__menu {
    display: flex;
      gap: 50px;
      &_link {
        color: #292F36;
        text-align: center;
        font-family: 'Jost';
        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: 125%; /* 25px */
        }
    }
}

.siteName {
  color: #292F36;
  font-family: 'DM Serif Display', sans-serif;
  font-size: 40px;
  font-style: normal;
  font-weight: 400;
  line-height: 125%; /* 50px */
}

.banner {
  display: flex;
  min-height: 758px;
  fill: #F4F0EC;
  background: url("./assets/img/content/ContentBlock1.png"), lightgray 5% / cover no-repeat;
  margin-top: 57px;
  border-radius: 80px;
  &__into {
    width: 595px;
    margin-left: 52px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    }
  &__subcontent {
    display: flex;
    flex-direction: column;
    gap: 18px;
    margin-bottom: 21px;
    &-head {
      color: #292F36;
      font-family: 'DM Serif Display', sans-serif;
      font-size: 65px;
      font-style: normal;
      font-weight: 400;
      line-height: 125%;
    }
    &-text {
      color: #292F36;
      font-family: 'Jost';
      font-size: 22px;
      font-style: normal;
      font-weight: 400;
      line-height: 150%; /* 33px */
      letter-spacing: 0.22px;
    }
  }
  .button {
    display: flex;
    padding: 26px 49px 26px 48px;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 10px;
    border-radius: 18px;
    background: #292F36;
    box-shadow: 0px 10px 20px 0px rgba(192, 192, 192, 0.35);
    color: #FFFFFF;
    text-align: center;
    font-family: 'Jost';
    font-size: 18px;
    font-style: normal;
    font-weight: 600;
    line-height: 125%; /* 22.5px */
    letter-spacing: 0.36px;
  }
}

.project {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 93px;
  margin-top: 96px;
  &__heading {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    max-width: 737px;
    &_title {
      color: #292F36;
      text-align: center;
      font-family: 'DM Serif Display', sans-serif;
      font-size: 50px;
      font-style: normal;
      font-weight: 400;
      line-height: 125%; /* 62.5px */
      letter-spacing: 1px;
    }
    &_subtitle {
      color: #292F36;
      text-align: center;
      font-family: 'Jost';
      font-size: 22px;
      font-style: normal;
      font-weight: 400;
      line-height: 150%; /* 33px */
      letter-spacing: 0.22px;
    }
  }
  &__content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 56px;
    &_block {
      display: flex;
      justify-content: center;
      align-items: flex-start;
      gap: 104px;
      &-img1 {
        width: 548px;
        height: 525px;
        // transform: rotate(90deg);
        flex-shrink: 0;
        border-radius: 0px 80px 0px 0px;
        background: #C4C4C4;
        background: url(./assets/img/content/Photo1Block2.jpg), lightgray 50% / cover no-repeat;
      };
      &-img2 {
        width: 548px;
        height: 525px;
        // transform: rotate(90deg);
        flex-shrink: 0;
        border-radius: 80px 0px 0px 0px;
        background: #C4C4C4;
        background: url(./assets/img/content/Photo2Block2.jpg), lightgray 50% / cover no-repeat;
      };
      &-img3 {
        width: 548px;
        height: 525px;
        // transform: rotate(90deg);
        flex-shrink: 0;
        border-radius: 0px 0px 80px 0px;
        background: #C4C4C4;
        background: url(./assets/img/content/Photo3Block2.jpg), lightgray 50% / cover no-repeat;
      };
      &-img4 {
        width: 548px;
        height: 525px;
        // transform: rotate(90deg);
        flex-shrink: 0;
        border-radius: 0px 0px 0px 80px;
        background: #C4C4C4;
        background: url(./assets/img/content/Photo4Block2.jpg), lightgray 50% / cover no-repeat;
      };
      &-left {
        display: flex;
        // width: 619px;
        // transform: rotate(-90deg);
        align-items: flex-start;
        gap: 24px;
        flex-shrink: 0;
        flex-direction: column;
      }
      &-right {
        display: flex;
        // width: 619px;
        // transform: rotate(-90deg);
        align-items: flex-start;
        gap: 24px;
        flex-shrink: 0;
        flex-direction: column;
      }
      &-nav {
        display: flex;
        width: 547px;
        // transform: rotate(90deg);
        align-items: center;
        gap: 227px;
        flex-shrink: 0;
      }
      &-text {
        display: flex;
        width: 250px;
        flex-direction: column;
        align-items: flex-start;
        gap: 4px;
        flex-shrink: 0;
        &_title {
          color: #292F36;
          font-family: 'DM Serif Display', sans-serif;
          font-size: 25px;
          font-style: normal;
          font-weight: 400;
          line-height: 125%; /* 31.25px */
          letter-spacing: 0.5px;
        }
        &_subtitle {
          color: #292F36;
          font-family: 'Jost';
          font-size: 22px;
          font-style: normal;
          font-weight: 400;
          line-height: 150%; /* 33px */
          letter-spacing: 0.22px;
        }
        &-imgButton {
          width: 70px;
          height: 70px;
          flex-shrink: 0;
        }
      }
      &-button>a {
        display: flex;
        color: #292F36;
        background-color: #f4f0ec;
        border-radius: 50px;
        height: 70px;
        width: 70px;
        align-items: center;
        justify-content: center;
        font-weight: 600;
      }
      &-button>a:hover {
        background: #ffffff00;
        color: #292F36;
        box-shadow: 0 0 0 2px #F4F0EC;
      }
    }
  }
}

.counter {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 457px;
  flex-shrink: 0;
  background-color: #F4F0EC;
  margin-top: 100px;
  width: 1920px;
  margin-left: 50%;
  transform: translateX(-50%);
  &__counters {
    display: flex;
    width: 1082px;
    justify-content: space-between;
    align-items: center;
    gap: 38px;
    &_block {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 16px;
    }
    &-cnt {
      color: #CDA274;
      font-family: 'DM Serif Display', sans-serif;
      font-size: 85px;
      font-style: normal;
      font-weight: 400;
      line-height: 125%; /* 106.25px */
      letter-spacing: 1.7px;
    }
    &-label {
      color: #292F36;
      font-family: 'Jost';
      font-size: 22px;
      font-style: normal;
      font-weight: 400;
      line-height: 150%; /* 33px */
      letter-spacing: 0.22px;
    }
  }
}

.blog {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 52px;
  &__heading {
    display: flex;
    flex-direction: column;
    margin-top: 96px;
    max-width: 811px;
    gap: 12px;
    &-title {
      color: #292F36;
      text-align: center;
      font-family: 'DM Serif Display', sans-serif;
      font-size: 50px;
      font-style: normal;
      font-weight: 400;
      line-height: 125%; /* 62.5px */
      letter-spacing: 1px;
    };
    &-subtitle {
      color: #292F36;
      text-align: center;
      font-family: 'Jost';
      font-size: 22px;
      font-style: normal;
      font-weight: 400;
      line-height: 150%; /* 33px */
      letter-spacing: 0.22px;
    }
  }
  &__blog-window {
    display: flex;
    width: 382px;
    // min-height: 551px;
    flex-shrink: 0;
  }
  &__blog {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: flex-start;
    gap: 27px;
      &_subcontent {
        display: inline-flex;
        padding: 21px 21px 37.7px 21px;
        align-items: flex-start;
        gap: 10px;
        border-radius: 62px;
        border: 1px solid #E7E7E7;
        box-shadow: 0px 10px 30px 0px rgba(255, 255, 255, 0.25);
      }
      &_subcontent:hover {
        background: #F4F0EC;
        fill: #FFFFFF;
      }
      &_content {
        display: flex;
        width: 340px;
        flex-direction: column;
        align-items: center;
        gap: 21px;
          &-img {
            display: flex;
            align-items: flex-end;
            border-radius: 45px 45px 0px 0px;
            background: url(./assets/img/content/Photo1Block3.png), lightgray 50% / cover no-repeat;
            width: 340px;
            height: 289.267px;
            flex-shrink: 0;
            &_tag {
              margin-left: 20px;
              margin-bottom: 20px;
              // width: 129px;
              // height: 41px;
              flex-shrink: 0;
              &-rectangle {
                // width: 124px;
                height: 41px;
                flex-shrink: 0;
                border-radius: 8px 8px 8px 0px;
                background: #fff;
                padding: 6px;
              }
              &-text {
                display: flex;
                // width: 223px;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                height: 33px;
                color: #292F36;
                font-family: 'Jost';
                font-size: 16px;
                font-style: normal;
                font-weight: 400;
                line-height: 150%; /* 24px */
                letter-spacing: 0.16px;
                text-transform: capitalize;
              }
            }
          }
          &-img2 {
            background: url(./assets/img/content/Photo2Block3.png), lightgray 50% / cover no-repeat;
          }
          &-img3 {
            background: url(./assets/img/content/Photo3Block3.png), lightgray 50% / cover no-repeat;
          }
          &-img4 {
            background: url(./assets/img/content/Blog4.jpg), lightgray 50% / cover no-repeat;
          }
          &-img5 {
            background: url(./assets/img/content/Blog5.jpg), lightgray 50% / cover no-repeat;
          }
          &-img6 {
            background: url(./assets/img/content/Blog6.jpg), lightgray 50% / cover no-repeat;
          }
          &-subcontent {
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            width: 340px;
            gap: 30px;
          }
          &-title {
            color: #292F36;
            font-family: 'DM Serif Display', sans-serif;
            width: 305px;
            min-height: 90px;
            font-size: 25px;
            font-style: normal;
            font-weight: 400;
            line-height: 125%; /* 31.25px */
            letter-spacing: 0.5px;
          }
            &-date {
                font-family: 'Jost';
                display: flex;
                width: 340px;
                align-items: center;
                gap: 65px;
                justify-content: space-between;
            }
        }
        &-imgButton {
            width: 52px;
            height: 52px;
        }
    }
}

.footer {
    display: flex;
    width: 1920px;
    margin-left: 50%;
    transform: translateX(-50%);
    flex-direction: column;
    align-items: center;
    gap: 134px;
    margin-top: 96px;
    &__interno {
        display: flex;
        width: 1199px;
        align-items: flex-start;
        gap: 101px;
        &_interno {
            display: flex;
            width: 393px;
            flex-direction: column;
            align-items: flex-start;
            gap: 31px;
            flex-shrink: 0;
            &-subcontent {
                display: flex;
                width: 393px;
                flex-direction: column;
                align-items: flex-start;
                gap: 18px;
            }
            &-text {
                color: #292F36;
                font-family: 'Jost';
                font-size: 22px;
                font-style: normal;
                font-weight: 400;
                line-height: 150%; /* 33px */
                letter-spacing: 0.22px;
            }
        }
        &_pages {
            display: flex;
            width: 125px;
            flex-direction: column;
            align-items: flex-start;
            gap: 9px;
            flex-shrink: 0;
            &-title {
                color: #292F36;
                font-family: 'DM Serif Display', sans-serif;
                font-size: 25px;
                font-style: normal;
                font-weight: 400;
                line-height: 125%; /* 31.25px */
            }
        }
        &_menu{
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            gap: 32px;
            margin-top: 32px;
        }
        &_services {
            display: flex;
            width: 120px;
            height: 66px;
            flex-direction: column;
            align-items: flex-start;
            gap: 9px;
            flex-shrink: 0;
        }
        &_contact {
            display: flex;
            width: 258px;
            flex-direction: column;
            align-items: flex-start;
            gap: 26px;
            flex-shrink: 0;
        }

    }
}
.social_links {
    display: flex;
    width: 225px;
    align-items: center;
    gap: 54px;
}

// Страница blog.html
.blogpage {
    &__banner {
        display: flex;
        flex-direction: row;
        justify-content: center;
        width: 1920px;
        height: 356px;
        flex-shrink: 0;
        margin-left: 50%;
        transform: translateX(-50%);
        background: url(./assets/img/content/bannerBlog.jpg), lightgray 50% / cover no-repeat;
        margin-top: 45px;
        &-into {
            display: flex;
            justify-content: center;
            width: 503px;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            border-radius: 37px 37px 0px 0px;
            background: #fff;
            margin-top: 178px;
        }
        &-intoHead {
            color: #292F36;
            font-family: 'DM Serif Display', sans-serif;
            font-size: 50px;
            font-style: normal;
            font-weight: 400;
            line-height: 125%; /* 62.5px */
        }
        &-breadcrumbs {
            color: #292F36;
            font-family: 'Jost';
            font-size: 22px;
            font-style: normal;
            font-weight: 400;
            line-height: 150%; /* 33px */
            letter-spacing: 0.22px;
        }
    }
    &__latestPost {
        display: flex;
        width: 1201px;
        flex-direction: column;
        align-items: flex-start;
        gap: 27px;
        margin-top: 200px;
    }
    &__heading-title{
        color: #292F36;
        font-family: 'DM Serif Display', sans-serif;
        font-size: 50px;
        font-style: normal;
        font-weight: 400;
        line-height: 125%; /* 62.5px */
        letter-spacing: 1px;
    }
    &__latestPost-card {
        display: flex;
        width: 1201px;
        padding: 22px;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 10px;
        border-radius: 62px;
        border: 1px solid #E7E7E7;
        box-shadow: 0px 10px 30px 0px rgba(255, 255, 255, 0.25);
    }
    &__latestPost-post {
        display: flex;
        width: 1157px;
        align-items: center;
        gap: 65px;
    }
    &__latestPost-img {
        width: 569px;
        height: 478px;
        flex-shrink: 0;
        background: #C4C4C4;
        background: url(./assets/img/content/Blog-LastNews.png), lightgray 50% / cover no-repeat;
        border-radius: 50px;
    }
    &__latestPost-content {
        display: flex;
        width: 489px;
        flex-direction: column;
        align-items: flex-start;
        gap: 41px;
        flex-shrink: 0;
    }
    &__latestPost-subcontent {
        display: flex;
        width: 469px;
        flex-direction: column;
        align-items: flex-start;
        gap: 22px;
    }
    &__latestPost-title {
        color: #292F36;
        font-family: 'DM Serif Display', sans-serif;
        font-size: 25px;
        font-style: normal;
        font-weight: 400;
        line-height: 125%; /* 31.25px */
        letter-spacing: 0.5px;
    }
    &__latestPost-text {
        color: #292F36;
        font-family: 'Jost';
        font-size: 22px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%; /* 33px */
        letter-spacing: 0.22px;
    }
    &__latestPost-date {
        display: flex;
        width: 489px;
        align-items: center;
        gap: 214px;
    }
    &__latestPost-date_text {
        color: #292F36;
        font-family: 'Jost';
        font-size: 16px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%; /* 24px */
        letter-spacing: 0.16px;
        text-transform: capitalize;
    }
    &__artcle-and-news {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 51px;
    }
    &__blog {
        display: flex;
        align-items: flex-start;
        margin-top: 150px;
        gap: 30px;
        margin-top: 0;
    }
    &__pagination {
        display: flex;
        width: 268px;
        justify-content: center;
        align-items: flex-start;
        gap: 20px;
        &-page {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 52px;
            height: 52px;
            flex-shrink: 0;
            // background: url(../img/logos/Ellipse\ 5.svg), lightgray 0% / cover no-repeat;
            border-radius: 50px;
            border: 2px;
            border: 1px solid #CDA274;
            color: #292F36;
            font-family: 'Jost';
            font-size: 16px;
            font-style: normal;
            font-weight: 500;
            line-height: 150%; /* 24px */
            text-transform: capitalize;
        }
        &-page:hover {
            background: url(./assets/img/logos/Ellipse\ 4.svg) lightgray 50% / cover no-repeat;
            border: none;

        }
    }
}

// Страница blog-details.html
.blog-details {
  &__banner {
    width: 1920px;
    height: 351px;
    flex-shrink: 0;
    margin-left: 50%;
    transform: translateX(-50%);
    background: url(./assets/img/content/Photo-blog.jpg), lightgray 50% / cover no-repeat;
    margin-top: 45px;
  }
  &__box {
    display: flex;
    margin-top: 200px;
  }
  &__blog {
    display: flex;
    width: 1200px;
    align-items: flex-start;
    gap: 52px;
    flex-direction: column;
  }

    &__sidebar {
        display: flex;
        width: 345px;
        flex-direction: column;
        align-items: flex-start;
        gap: 50px;
        flex-shrink: 0;
    }
    &__sidebar-tags {
        display: flex;
        width: 345px;
        flex-direction: column;
        align-items: flex-start;
        gap: 24px;
    }
    &__sidebar-title {
        color: #292F36;
        font-family: 'DM Serif Display', sans-serif;
        font-size: 25px;
        font-style: normal;
        font-weight: 400;
        line-height: 125%; /* 31.25px */
        letter-spacing: 0.5px;
    }
    &__sidebar-content {
        display: flex;
        width: 335px;
        flex-direction: row;
        flex-wrap: wrap;
        align-items: flex-start;

        gap: 11px;
    }
    &__sidebar-contentBlock {
        display: flex;
        align-items: flex-start;
        gap: 10px;
    }
    &__sidebar-button {
        display: flex;
        padding: 9px 30px;
        justify-content: center;
        align-items: center;
        gap: 10px;
        border-radius: 10px;
        background: #F4F0EC;
        color: #292F36;
        text-align: center;
        font-family: 'Jost';
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 125%; /* 22.5px */
        letter-spacing: 0.36px;
        & input[type="radio"] {
            display: none;
        }
    }
    &__sidebar-buttonA {
        background: #292f36;
        display: none;
    }
    &__sidebar-button:hover, &__sidebar-button:active {
        color: #FFF;
        background: #292F36;
    }
    &__details {
        width: 804px;
        display: flex;
    }
    &__details-content {
        display: flex;
        width: 800px;
        flex-direction: column;
        align-items: flex-start;
        gap: 48px;
    }
    &__details-subcontent {
        display: flex;
        width: 800px;
        flex-direction: column;
        align-items: flex-start;
        gap: 46px;
    }
    &__details-subSubcontent {
        display: flex;
        width: 799px;
        flex-direction: column;
        align-items: flex-start;
        gap: 21px;
    }
    &__details-title {
        color: #292F36;
        font-family: 'DM Serif Display', sans-serif;
        font-size: 50px;
        font-style: normal;
        font-weight: 400;
        line-height: 125%; /* 62.5px */
        letter-spacing: 1px;
    }
    &__details-img {
        width: 799px;
        height: 539px;
        border-radius: 50px;
        background: #C4C4C4;
        border-radius: 50px;
        // background: url(../img/content/PhotoBlog1.png), lightgray 50% / cover no-repeat;
    }
    &__details-subcontentDate {
        display: flex;
        align-items: center;
        gap: 409px;
    }
    &__details-date, &__details-bradcrumbs{
        display: flex;
        flex-direction: column;
        justify-content: center;
        color: #292F36;
        font-family: 'Jost';
        font-size: 16px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%; /* 24px */
        letter-spacing: 0.16px;
        text-transform: capitalize;
    }
    &__details-text {
        color: #292F36;
        font-family: 'Jost';
        font-size: 22px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%; /* 33px */
        letter-spacing: 0.22px;
    }

    &__details-quotes {
        display: flex;
        width: 799px;
        padding: 53px 227px;
        flex-direction: column;
        align-items: center;
        gap: 10px;
        border-radius: 50px;
        background: #F4F0EC;
        margin-top: 35px;
    }
    &__details-quotesContent {

        color: #CDA274;
    }
    &__details-quotesContentText {
        display: flex;
        color: #CDA274;
        text-align: center;
        font-family: 'DM Serif Display', sans-serif;
        font-size: 25px;
        font-style: italic;
        font-weight: 400;
        line-height: 125%; /* 31.25px */
        letter-spacing: 0.5px;
    }
    &__details-quotesContentSymbol {
        color: #CDA274;
        text-align: center;
        font-family: 'DM Serif Display', sans-serif;
        font-style: italic;
        font-weight: 400;
        line-height: 125%; /* 250px */
        letter-spacing: 4px;
    }
    &__details-subcontentPart2 {
        gap:24;
        margin-top: 27px;
    }
    &__details-points {
        display: flex;
        width: 732.389px;
        flex-direction: column;
        align-items: flex-start;
        gap: 32px;
    }
    &__details-point {
        display: flex;
        width: 732.389px;
        align-items: flex-start;
        gap: 14px;
    }
    &__details-pointNumber {
        width: 5.389px;
        flex-shrink: 0;
        color: #CDA274;
        font-family: 'DM Serif Display', sans-serif;
        font-size: 20px;
        font-style: normal;
        font-weight: 400;
        line-height: 125%; /* 25px */
        letter-spacing: 0.4px;
    }
    &__details-subSubcontent {
        display: flex;
        width: 799px;
        flex-direction: column;
        align-items: flex-start;
        gap: 35px;
    }
    &__details-subSubcontentImg {
        width: 799px;
        height: 365px;
        border-radius: 50px;
        background: #C4C4C4;
        background: url(./assets/img/content/PhotoBlog2.png), lightgray 50% / cover no-repeat;
    }
}

// Страница project-page.html
.project-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  &__banner {
        display: flex;
        flex-direction: row;
        justify-content: center;
        width: 1920px;
        height: 356px;
        flex-shrink: 0;
        margin-left: 50%;
        transform: translateX(-50%);
        background: url(./assets/img/content/Project-page.jpg), lightgray 50% / cover no-repeat;
        margin-top: 45px;
        &-into {
            display: flex;
            justify-content: center;
            width: 503px;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            border-radius: 37px 37px 0px 0px;
            background: #fff;
            margin-top: 178px;
        }
        &-intoHead {
            color: #292F36;
            font-family: 'DM Serif Display', sans-serif;
            font-size: 50px;
            font-style: normal;
            font-weight: 400;
            line-height: 125%; /* 62.5px */
        }
        &-breadcrumbs {
            color: #292F36;
            font-family: 'Jost';
            font-size: 22px;
            font-style: normal;
            font-weight: 400;
            line-height: 150%; /* 33px */
            letter-spacing: 0.22px;
        }
  }
  &__box {
    display: flex;
    margin-top: 200px;
    flex-direction: column;
    align-items: center;
  }
  &__blog-box {
    column-count: 2!important;
    // margin-top: 61px;
    // display: grid;
    // grid-template-columns: auto auto;
    // column-gap: 30px;
    // row-gap: 35px;
  }
  &__blog {
    display: flex;
    width: 585px;
    align-items: flex-start;
    gap: 52px;
    flex-direction: column;
    border: none !important;
  }
  &__sidebar {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      gap: 50px;
      flex-shrink: 0;
  }
  &__sidebar-tags {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      gap: 24px;
  }
  &__sidebar-title {
      color: #292F36;
      font-family: 'DM Serif Display', sans-serif;
      font-size: 25px;
      font-style: normal;
      font-weight: 400;
      line-height: 125%; /* 31.25px */
      letter-spacing: 0.5px;
  }
  &__sidebar-content {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      align-items: flex-start;

      gap: 11px;
  }
  &__sidebar-contentBlock {
      display: flex;
      align-items: flex-start;
      gap: 10px;
  }
  &__sidebar-button {
      display: flex;
      padding: 9px 30px;
      justify-content: center;
      align-items: center;
      gap: 10px;
      border-radius: 10px;
      background: #F4F0EC;
      color: #292F36;
      text-align: center;
      font-family: 'Jost';
      font-size: 18px;
      font-style: normal;
      font-weight: 400;
      line-height: 125%; /* 22.5px */
      letter-spacing: 0.36px;
      & input[type="radio"] {
          display: none;
      }
  }
  &__sidebar-buttonA {
      background: #292f36;
      display: none;
  }
  &__sidebar-button:hover, &__sidebar-button:active {
      color: #FFF;
      background: #292F36;
  }
  &__details {
      width: 585px;
      display: flex;
  }
  &__details-content {
      display: flex;
      width: 585px;
      flex-direction: column;
      align-items: flex-start;
      gap: 24px;
  }
  &__details-subcontent {
      display: flex;
      width: 585px;
      flex-direction: column;
      align-items: flex-start;
      gap: 46px;
  }
  &__details-subSubcontent {
      display: flex;
      width: 585px;
      flex-direction: column;
      align-items: flex-start;
  }
  &__details-title {
      color: #292F36;
      font-family: 'DM Serif Display', sans-serif;
      font-size: 25px;
      font-style: normal;
      font-weight: 400;
      line-height: 125%; /* 62.5px */
      letter-spacing: 1px;
  }
  &__details-img {
      width: 585px;
      background: #C4C4C4;
      // background: url(../img/content/PhotoBlog1.png), lightgray 50% / cover no-repeat;
  }
  &__card-footer {
      display: flex;
      align-items: center;
      width: 585px;
      justify-content: space-between;
  }
  &__details-subcontentDate {
      display: flex;
      flex-direction: column;
      gap: 4px;
      flex-wrap: wrap;
  }
  &__details-date, &__details-bradcrumbs{
      display: flex;
      flex-direction: column;
      justify-content: center;
      color: #4D5053;
      font-family: 'Jost';
      font-size: 22px;
      font-style: normal;
      font-weight: 400;
      line-height: 150%; /* 24px */
      letter-spacing: 0.16px;
      text-transform: capitalize;
  }
  &__details-text {
      color: #292F36;
      font-family: 'Jost';
      font-size: 22px;
      font-style: normal;
      font-weight: 400;
      line-height: 150%; /* 33px */
      letter-spacing: 0.22px;
  }
  &__details-quotes {
      display: flex;
      width: 799px;
      padding: 53px 227px;
      flex-direction: column;
      align-items: center;
      gap: 10px;
      border-radius: 50px;
      background: #F4F0EC;
      margin-top: 35px;
  }
  &__details-quotesContent {

      color: #CDA274;
  }
  &__details-quotesContentText {
      display: flex;
      color: #CDA274;
      text-align: center;
      font-family: 'DM Serif Display', sans-serif;
      font-size: 25px;
      font-style: italic;
      font-weight: 400;
      line-height: 125%; /* 31.25px */
      letter-spacing: 0.5px;
  }
  &__details-quotesContentSymbol {
      color: #CDA274;
      text-align: center;
      font-family: 'DM Serif Display', sans-serif;
      font-style: italic;
      font-weight: 400;
      line-height: 125%; /* 250px */
      letter-spacing: 4px;
  }
  &__details-subcontentPart2 {
      gap:24;
      margin-top: 27px;
  }
  &__details-points {
      display: flex;
      width: 732.389px;
      flex-direction: column;
      align-items: flex-start;
      gap: 32px;
  }
  &__details-point {
      display: flex;
      width: 732.389px;
      align-items: flex-start;
      gap: 14px;
  }
  &__details-pointNumber {
      width: 5.389px;
      flex-shrink: 0;
      color: #CDA274;
      font-family: 'DM Serif Display', sans-serif;
      font-size: 20px;
      font-style: normal;
      font-weight: 400;
      line-height: 125%; /* 25px */
      letter-spacing: 0.4px;
  }
  // &__details-subSubcontent {
  //     display: flex;
  //     width: 799px;
  //     flex-direction: column;
  //     align-items: flex-start;
  //     gap: 35px;
  // }
  &__details-subSubcontentImg {
      width: 799px;
      height: 365px;
      border-radius: 50px;
      background: #C4C4C4;
      background: url(./assets/img/content/PhotoBlog2.png), lightgray 50% / cover no-repeat;
  }
  &__pagination {
      display: flex;
      width: 268px;
      justify-content: center;
      align-items: flex-start;
      gap: 20px;
      &-page {
          display: flex;
          justify-content: center;
          align-items: center;
          width: 52px;
          height: 52px;
          flex-shrink: 0;
          // background: url(../img/logos/Ellipse\ 5.svg), lightgray 0% / cover no-repeat;
          border-radius: 50px;
          border: 2px;
          border: 1px solid #CDA274;
          color: #292F36;
          font-family: 'Jost';
          font-size: 16px;
          font-style: normal;
          font-weight: 500;
          line-height: 150%; /* 24px */
          text-transform: capitalize;
      }
      &-page:hover {
          background: url(./assets/img/logos/Ellipse\ 4.svg) lightgray 50% / cover no-repeat;
          border: none;

      }
  }
}

// Страница project-details.html
.project-details {
  &__banner {
    width: 1920px;
    height: 351px;
    flex-shrink: 0;
    margin-left: 50%;
    transform: translateX(-50%);
    background: url(./assets/img/content/Photo-blog.jpg), lightgray 50% / cover no-repeat;
    margin-top: 45px;
  }
  &__box {
    display: flex;
    margin-top: 200px;
  }
  &__blog {
    display: flex;
    width: 1200px;
    align-items: flex-start;
    gap: 52px;
    flex-direction: column;
  }
  &__sidebar {
      display: flex;
      width: 345px;
      flex-direction: column;
      align-items: flex-start;
      gap: 50px;
      flex-shrink: 0;
  }
  &__sidebar-tags {
      display: flex;
      width: 345px;
      flex-direction: column;
      align-items: flex-start;
      gap: 24px;
  }
  &__sidebar-title {
      color: #292F36;
      font-family: 'DM Serif Display', sans-serif;
      font-size: 25px;
      font-style: normal;
      font-weight: 400;
      line-height: 125%; /* 31.25px */
      letter-spacing: 0.5px;
  }
  &__sidebar-content {
      display: flex;
      width: 335px;
      flex-direction: row;
      flex-wrap: wrap;
      align-items: flex-start;

      gap: 11px;
  }
  &__sidebar-contentBlock {
      display: flex;
      align-items: flex-start;
      gap: 10px;
  }
  &__sidebar-button {
      display: flex;
      padding: 9px 30px;
      justify-content: center;
      align-items: center;
      gap: 10px;
      border-radius: 10px;
      background: #F4F0EC;
      color: #292F36;
      text-align: center;
      font-family: 'Jost';
      font-size: 18px;
      font-style: normal;
      font-weight: 400;
      line-height: 125%; /* 22.5px */
      letter-spacing: 0.36px;
      & input[type="radio"] {
          display: none;
      }
  }
  &__sidebar-buttonA {
      background: #292f36;
      display: none;
  }
  &__sidebar-button:hover, &__sidebar-button:active {
      color: #FFF;
      background: #292F36;
  }
  &__details {
      width: 804px;
      display: flex;
  }
  &__details-content {
      display: flex;
      width: 800px;
      flex-direction: column;
      align-items: flex-start;
      gap: 48px;
  }
  &__details-subcontent {
      display: flex;
      width: 800px;
      flex-direction: column;
      align-items: flex-start;
      gap: 46px;
  }
  &__details-subSubcontent {
      display: flex;
      width: 799px;
      flex-direction: column;
      align-items: flex-start;
      gap: 21px;
  }
  &__details-title {
      color: #292F36;
      font-family: 'DM Serif Display', sans-serif;
      font-size: 50px;
      font-style: normal;
      font-weight: 400;
      line-height: 125%; /* 62.5px */
      letter-spacing: 1px;
  }
  &__details-img {
      width: 799px;
      height: 539px;
      border-radius: 50px;
      background: #C4C4C4;
      border-radius: 50px;
      // background: url(../img/content/PhotoBlog1.png), lightgray 50% / cover no-repeat;
  }
  &__details-subcontentDate {
      display: flex;
      align-items: center;
      gap: 409px;
  }
  &__details-date, &__details-bradcrumbs{
      display: flex;
      flex-direction: column;
      justify-content: center;
      color: #292F36;
      font-family: 'Jost';
      font-size: 16px;
      font-style: normal;
      font-weight: 400;
      line-height: 150%; /* 24px */
      letter-spacing: 0.16px;
      text-transform: capitalize;
  }
  &__details-text {
      color: #292F36;
      font-family: 'Jost';
      font-size: 22px;
      font-style: normal;
      font-weight: 400;
      line-height: 150%; /* 33px */
      letter-spacing: 0.22px;
  }
  &__details-quotes {
      display: flex;
      width: 799px;
      padding: 53px 227px;
      flex-direction: column;
      align-items: center;
      gap: 10px;
      border-radius: 50px;
      background: #F4F0EC;
      margin-top: 35px;
  }
  &__details-quotesContent {

      color: #CDA274;
  }
  &__details-quotesContentText {
      display: flex;
      color: #CDA274;
      text-align: center;
      font-family: 'DM Serif Display', sans-serif;
      font-size: 25px;
      font-style: italic;
      font-weight: 400;
      line-height: 125%; /* 31.25px */
      letter-spacing: 0.5px;
  }
  &__details-quotesContentSymbol {
      color: #CDA274;
      text-align: center;
      font-family: 'DM Serif Display', sans-serif;
      font-style: italic;
      font-weight: 400;
      line-height: 125%; /* 250px */
      letter-spacing: 4px;
  }
  &__details-subcontentPart2 {
      gap:24;
      margin-top: 27px;
  }
  &__details-points {
      display: flex;
      width: 732.389px;
      flex-direction: column;
      align-items: flex-start;
      gap: 32px;
  }
  &__details-point {
      display: flex;
      width: 732.389px;
      align-items: flex-start;
      gap: 14px;
  }
  &__details-pointNumber {
      width: 5.389px;
      flex-shrink: 0;
      color: #CDA274;
      font-family: 'DM Serif Display', sans-serif;
      font-size: 20px;
      font-style: normal;
      font-weight: 400;
      line-height: 125%; /* 25px */
      letter-spacing: 0.4px;
  }
  &__details-subSubcontent {
      display: flex;
      width: 799px;
      flex-direction: column;
      align-items: flex-start;
      gap: 35px;
  }
  &__details-subSubcontentImg {
      width: 799px;
      height: 365px;
      border-radius: 50px;
      background: #C4C4C4;
      background: url(./assets/img/content/PhotoBlog2.png), lightgray 50% / cover no-repeat;
  }
}
</style>
