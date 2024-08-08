<template>
  <div class="container">
    <div class="project-page__box">
      <div class="project-page__sidebar">
        <div class="project-page__sidebar-tags">
          <div class="project-page__sidebar-content">
            <div
              v-for="button in uniqueTags"
              :key="button.id"
              class="project-page__sidebar-contentBlock"
            >
              <!-- <div class="project-page__sidebar-button"> -->
                <button
                  :data-id="button.id"
                  @click="buttonName = button.tag, filterByTag, $router.push('/project-page').catch(()=>{})"
                  class="project-page__sidebar-button"
                >
                {{ button.tagName }}
                </button>
              <!-- </div> -->
            </div>
          </div>
        </div>
      </div>
      <b-card-group columns class="project-page__blog-box">
        <b-card
          class="project-page__blog"
          v-for="article in paginatedProjects"
          :key="article.id"
        >
          <div class="project-page__detais">
            <div class="project-page__details-content">
              <div class="project-page__details-subcontent">
                <div class="project-page__details-subSubcontent">
                  <div>
                    <img
                      :src="article.src"
                      :alt="article.alt"
                      class="project-page__details-img"
                    >
                  </div>
                </div>
                <div class="project-page__card-footer">
                  <div class="project-page__details-subcontentDate">
                    <div class="project-page__details-title">
                      {{ article.title }}
                    </div>
                    <div class="project-page__details-bradcrumbs">
                      {{ article.link }}
                    </div>
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
        </b-card>
      </b-card-group>
      <div class="project-page__pagination">
        <router-link class="project-page__pagination-page"
          v-for="page in totalPages"
          :key="page"
          :to="`/project-page/${page}`"
        >
          {{ page }}
        </router-link>
        <!-- <div class="project-page__pagination-page">
          01
        </div>
        <div class="project-page__pagination-page">
          02
        </div>
        <div class="project-page__pagination-page">
          03
        </div>
        <div class="project-page__pagination-page">
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
        </div> -->
      </div>
      <div>
        <!-- {{ this.buttonName }} -->
        <!-- {{ filterByTag }} -->
        <!-- {{ uniqueTags }} -->
        <!-- {{ this.articles }} -->
        <!-- {{ articles }} -->
      </div>
    </div>
  </div>
</template>

<script>
// import image1 from '@/assets/img/content/Project/Project1.jpg'
// import image2 from '@/assets/img/content/Project/Project2.jpg'
// import image3 from '@/assets/img/content/Project/Project3.jpg'
// import image4 from '@/assets/img/content/Project/Project4.jpg'
// import image5 from '@/assets/img/content/Project/Project5.jpg'
// import image6 from '@/assets/img/content/Project/Project6.jpg'
// import image7 from '@/assets/img/content/Project/Project7.jpg'
// import image8 from '@/assets/img/content/Project/Project8.jpg'
import { mapActions, mapGetters } from 'vuex'

export default {
  name: 'ProjectBlock',
  data () {
    return {
      buttonName: '',
      sortedArray: [
      ],
      // articles: [
      //   {
      //     id: '1',
      //     tag: 'kitchen',
      //     title: 'Минималистичная спальня',
      //     date: '26 Декабрь,2022',
      //     link: 'Декор / Планировка',
      //     firstpargth: 'В своей статье от 1994-го года журнал «Before & After» отследил фразу «Lorem ipsum ...» до философского трактата Цицерона О пределах добра и зла, написанного в 45 году до нашей эры на латинском языке. ',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image1,
      //     alt: 'photo',
      //     quote: 'Какая-то умная и красивая цитата',
      //     subtitle: 'Design sprints are great',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image2
      //   },
      //   {
      //     id: '2',
      //     tag: 'kitchen',
      //     title: 'Минималистичная спальня',
      //     date: '26 Декабрь,2022',
      //     link: 'Декор / Планировка',
      //     firstpargth: 'В своей статье от 1994-го года журнал «Before & After» отследил фразу «Lorem ipsum ...» до философского трактата Цицерона О пределах добра и зла, написанного в 45 году до нашей эры на латинском языке. ',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image2,
      //     alt: 'photo',
      //     quote: 'Какая-то умная и красивая цитата',
      //     subtitle: 'Design sprints are great',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image2
      //   },
      //   {
      //     id: '3',
      //     tag: 'kitchen',
      //     title: 'Классическая спальня',
      //     date: '26 Декабрь,2022',
      //     link: 'Декор / Планировка',
      //     firstpargth: 'В своей статье от 1994-го года журнал «Before & After» отследил фразу «Lorem ipsum ...» до философского трактата Цицерона О пределах добра и зла, написанного в 45 году до нашей эры на латинском языке. ',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image3,
      //     alt: 'photo',
      //     quote: 'Какая-то умная и красивая цитата',
      //     subtitle: 'Design sprints are great',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image2
      //   },
      //   {
      //     id: '4',
      //     tag: 'kitchen',
      //     title: 'Современная спальня',
      //     date: '26 Декабрь,2022',
      //     link: 'Декор / Планировка',
      //     firstpargth: 'В своей статье от 1994-го года журнал «Before & After» отследил фразу «Lorem ipsum ...» до философского трактата Цицерона О пределах добра и зла, написанного в 45 году до нашей эры на латинском языке. ',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image4,
      //     alt: 'photo',
      //     quote: 'Какая-то умная и красивая цитата',
      //     subtitle: 'Design sprints are great',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image2
      //   },
      //   {
      //     id: '5',
      //     tag: 'kitchen',
      //     title: 'Минималистичный прикроватный столик',
      //     date: '26 Декабрь,2022',
      //     link: 'Декор / Планировка',
      //     firstpargth: 'В своей статье от 1994-го года журнал «Before & After» отследил фразу «Lorem ipsum ...» до философского трактата Цицерона О пределах добра и зла, написанного в 45 году до нашей эры на латинском языке. ',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image5,
      //     alt: 'photo',
      //     quote: 'Какая-то умная и красивая цитата',
      //     subtitle: 'Design sprints are great',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image2
      //   },
      //   {
      //     id: '6',
      //     tag: 'kitchen',
      //     title: 'Столы и столики',
      //     date: '26 Декабрь,2022',
      //     link: 'Декор / Планировка',
      //     firstpargth: 'В своей статье от 1994-го года журнал «Before & After» отследил фразу «Lorem ipsum ...» до философского трактата Цицерона О пределах добра и зла, написанного в 45 году до нашей эры на латинском языке. ',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image6,
      //     alt: 'photo',
      //     quote: 'Какая-то умная и красивая цитата',
      //     subtitle: 'Design sprints are great',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image2
      //   },
      //   {
      //     id: '7',
      //     tag: 'kitchen',
      //     title: 'Современная спальня',
      //     date: '26 Декабрь,2022',
      //     link: 'Декор / Планировка',
      //     firstpargth: 'В своей статье от 1994-го года журнал «Before & After» отследил фразу «Lorem ipsum ...» до философского трактата Цицерона О пределах добра и зла, написанного в 45 году до нашей эры на латинском языке. ',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image7,
      //     alt: 'photo',
      //     quote: 'Какая-то умная и красивая цитата',
      //     subtitle: 'Design sprints are great',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image2
      //   },
      //   {
      //     id: '8',
      //     tag: 'kitchen',
      //     title: 'Современная спальня',
      //     date: '26 Декабрь,2022',
      //     link: 'Декор / Планировка',
      //     firstpargth: 'В своей статье от 1994-го года журнал «Before & After» отследил фразу «Lorem ipsum ...» до философского трактата Цицерона О пределах добра и зла, написанного в 45 году до нашей эры на латинском языке. ',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image8,
      //     alt: 'photo',
      //     quote: 'Какая-то умная и красивая цитата',
      //     subtitle: 'Design sprints are great',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image2
      //   },
      //   {
      //     id: '9',
      //     tag: 'kitchen',
      //     title: 'Создадим лучший макет перепланировки',
      //     date: '26 Декабрь,2022',
      //     link: 'Интерьер / Домой / Декор',
      //     firstpargth: 'В своей статье от 1994-го года журнал «Before & After» отследил фразу «Lorem ipsum ...» до философского трактата Цицерона О пределах добра и зла, написанного в 45 году до нашей эры на латинском языке. ',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image1,
      //     alt: 'photo',
      //     quote: 'Какая-то умная и красивая цитата',
      //     subtitle: 'Design sprints are great',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image2
      //   },
      //   {
      //     id: '10',
      //     tag: 'bedroom',
      //     title: 'Недорогие новейшие идеи дизайна интерьера.',
      //     date: '22 Декабрь,2022',
      //     link: 'Интерьер / Домой / Декор',
      //     firstpargth: 'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don t look even slightly believable.',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image5,
      //     alt: 'photo',
      //     quote: 'Какая-то умная и красивая цитата',
      //     subtitle: 'Design sprints are great',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image6
      //   },
      //   {
      //     id: '11',
      //     tag: 'building',
      //     title: 'Здание, обычно крытое и имеющее стены сооружение, возводимое для постоянного использования.',
      //     date: '20 Декабрь,2022',
      //     link: 'Страна / Город / Здание',
      //     firstpargth: 'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don t look even slightly believable.',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image7,
      //     alt: 'photo',
      //     quote: 'Хорошие здания строят хорошие люди, а все проблемы решаются хорошим проектированием.',
      //     subtitle: 'Мы формируем наши здания, а затем они формируют нас.',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image8
      //   },
      //   {
      //     id: '12',
      //     tag: 'architecture',
      //     title: 'В нашей статье подчеркивается важность планировки кухни для содействия соблюдению потребителями правил гигиены питания.',
      //     date: '29 Декабрь,2022',
      //     link: 'Страна / Город / Архитектура',
      //     firstpargth: 'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don t look even slightly believable.',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image8,
      //     alt: 'photo',
      //     quote: 'Архитектура — это визуальное искусство, и здания говорят сами за себя.',
      //     subtitle: 'Архитектура со всего мира от современных архитекторов, включая ультрасовременные дома, небоскребы, культурные здания, отели, аэропорты, квартиры.',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image6
      //   },
      //   {
      //     id: '13',
      //     tag: 'kitchen-planning',
      //     title: 'Планировка кухни: выбор правильной планировки',
      //     date: '25 Декабрь,2022',
      //     link: 'Интерьер / Дом / Кухня',
      //     firstpargth: 'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don t look even slightly believable.',
      //     secondpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     src: image2,
      //     alt: 'photo',
      //     quote: 'Кухня — это сердце дома.',
      //     subtitle: 'Кухни должны быть спроектированы с учетом того, что действительно важно — веселья, еды и жизни.',
      //     thirdpargth: 'В оригинале текст выглядит так «Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit ...», и переводится как «Нет никого, кто любил бы свою боль, кто искал бы ее и хотел бы чтобы она была у него. Потому что это боль...»',
      //     firstnumber: '1',
      //     secondnumber: '2',
      //     thirdnumber: '3',
      //     fourthpargth: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.',
      //     secondsrc: image3
      //   }
      // ],
      numbersandtexts: [
        {
          number: '1',
          text: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.'
        },
        {
          number: '2',
          text: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.'
        },
        {
          number: '3',
          text: 'С того времени этот, похожий на латинский, текст стал стандартом в печатной промышленности для примеров шрифтов и текстов.'
        }
      ],
      buttons: [
        {
          tag: 'kitchen',
          tagName: 'Кухня'
        },
        {
          tag: 'bedroom',
          tagName: 'Спальня'
        },
        {
          tag: 'building',
          tagName: 'Здание'
        },
        {
          tag: 'architecture',
          tagName: 'Архитектура'
        },
        {
          tag: 'kitchen-planning',
          tagName: 'Планировка'
        }
      ],
      perPage: 8
      // uniqueTags: []
    }
  },
  computed: {
    // ...mapState(['articles']),
    filterByTag () {
      if (this.buttonName === '') {
        return this.articles
      } else {
        return this.articles.filter(x => this.buttonName.indexOf(x.tag.toString()) !== -1)
      }
    },
    uniqueTags () {
      return this.articles.reduce((accumulator, current) => {
        if (accumulator.findIndex(object => object.tag === current.tag) === -1) {
          accumulator.push(current)
        }
        return accumulator
      }, [])
    },
    ...mapGetters(['articles']),
    currentPage () {
      const page = this.$route.params.page
      return page || 1
    },
    totalPages () {
      return Math.ceil(this.filterByTag.length / this.perPage)
    },
    paginatedProjects () {
      const { currentPage, perPage } = this
      const startIndex = (currentPage - 1) * perPage
      const endIndex = startIndex + perPage

      return this.filterByTag.slice(startIndex, endIndex)
    }
  },

  mounted () {
    this.fetchData()
    // this.uniqueTags = this.articles.reduce((accumulator, current) => {
    //   if (accumulator.findIndex(object => object.tag === current.tag) === -1) {
    //     accumulator.push(current)
    //   }
    //   return accumulator
    // }, [])
  },

  methods: {
    ...mapActions(['fetchData'])
    // sortArticles (e) {
    //   console.log(e.target)
    //   if (document.querySelector('.project-page__sidebar-button:active') !== null) {
    //     document.querySelector('.project-page__sidebar-button:active').classList.remove('project-page__sidebar-button')
    //   }
    //   const divButton = e.target.closest('.project-page__sidebar-button:active')
    //   divButton.classList.add('project-page__sidebar-button')
    // },
    // filters (e) {
    //   // console.log(e.target.dataset.id)
    //   this.sortedArray = this.articles.filter(articles => articles.tag === e.target.dataset.id)
    // }
  },

  created () {
    // this.sortedArray = this.articles
  }
}
</script>

<style lang="scss" scoped>

</style>
