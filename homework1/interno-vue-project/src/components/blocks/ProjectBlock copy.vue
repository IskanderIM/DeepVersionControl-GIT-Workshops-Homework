<template>
  <div class="container">
    <div class="project-page__box">
      <div class="project-page__sidebar">
        <div class="project-page__sidebar-tags">
          <div class="project-page__sidebar-content">
            <div
              v-for="button in buttons"
              :key="button.id"
              class="project-page__sidebar-contentBlock"
            >
              <div class="project-page__sidebar-button">
                <label
                  data-id="button.id"
                >
                  <input
                    :data-id="button.id"
                    @click="filters"
                    class="project-page__input"
                    type="radio"
                    name="radio"
                  >
                  {{ button.text }}
                </label>
              </div>
            </div>
          </div>
        </div>
      </div>
      <b-card-group columns class="project-page__blog-box">
        <b-card
          class="project-page__blog"
          v-for="article in sortedArray"
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
              <!-- <div class="project-page__details-text">
                {{ article.firstpargth }}<br><br>
                {{ article.secondpargth }}
              </div> -->
            </div>
          </div>
          <!-- <div class="project-page__details-quotes">
            <div class="project-page__details-quotesContent">
              <div class="project-page__details-quotesContentSymbol">
                <svg
                  width="74"
                  height="56"
                  viewBox="0 0 74 56"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M58.7516 0.600003C63.1516 0.600003 66.7516 2.06667 69.5516 5C72.2182 7.93334 73.5516 11.8667 73.5516 16.8C73.5516 25.4667 70.6849 33 64.9516 39.4C59.0849 45.8 52.0849 51.0667 43.9516 55.2L41.9516 51.8C45.2849 49.6667 48.4182 46.9333 51.3516 43.6C54.1516 40.2667 56.3516 36.6667 57.9516 32.8L52.3516 28.6C50.0849 27.1333 48.2182 25.1333 46.7516 22.6C45.2849 20.2 44.5516 17.8667 44.5516 15.6C44.5516 11.3333 45.8849 7.73334 48.5516 4.8C51.0849 2 54.4849 0.600003 58.7516 0.600003ZM17.5516 0.599999C21.9516 0.6 25.5516 2.06667 28.3516 5C31.0182 7.93333 32.3516 11.8667 32.3516 16.8C32.3516 25.4667 29.4849 33 23.7516 39.4C17.8849 45.8 10.8849 51.0667 2.75156 55.2L0.751558 51.8C4.08489 49.6667 7.21823 46.9333 10.1516 43.6C12.9516 40.2667 15.1516 36.6667 16.7516 32.8L11.1516 28.6C8.88489 27.1333 7.01823 25.1333 5.55156 22.6C4.08489 20.2 3.35156 17.8667 3.35156 15.6C3.35156 11.3333 4.6849 7.73333 7.35156 4.8C9.8849 2 13.2849 0.599999 17.5516 0.599999Z"
                    fill="#CDA274"
                  />
                </svg>
              </div>
              <div class="project-page__details-quotesContentText">
                {{ article.quote }}
              </div>
            </div>
          </div>
          <div class="project-page__details-content">
            <div class="project-page__details-subcontent">
              <div class="project-page__details-subcontentPart2">
                <div class="project-page__details-title">
                  {{ article.subtitle }}
                </div>
              </div>
              <div class="project-page__details-text">
                {{ article.thirdpargth }}
              </div>
              <div
                class="project-page__details-points"
                v-for="numberandtext in numbersandtexts"
                :key="numberandtext.id"
              >
                <div class="project-page__details-point">
                  <div class="project-page__details-pointNumber">
                    {{ numberandtext.number }}
                  </div>
                  <div class="project-page__details-text">
                    {{ numberandtext.text }}
                  </div>
                </div>
              </div>
            </div>
            <div class="project-page__details-subcontent">
              <div class="project-page__details-subSubcontent">
                <div>
                  <img
                    class="project-page__details-subSubcontentImg"
                    :src="article.secondsrc"
                    :alt="article.alt"
                  >
                </div>
                <div class="project-page__details-text">
                  {{ article.thirdpargth }}
                </div>
              </div>
            </div>
          </div> -->
        </b-card>
      </b-card-group>
      <div class="project-page__pagination">
        <div class="project-page__pagination-page">
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
        </div>
      </div>
      <div>
        {{ unique }}
        {{ this.actions }}
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
import { mapGetters } from 'vuex'

export default {
  name: 'ProjectBlock',
  data () {
    return {
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
          id: 'kitchen',
          text: 'Кухня'
        },
        {
          id: 'bedroom',
          text: 'Спальня'
        },
        {
          id: 'building',
          text: 'Здание'
        },
        {
          id: 'architecture',
          text: 'Архитектура'
        },
        {
          id: 'kitchen-planning',
          text: 'Планировка'
        }
      ],
      unique: []
    }
  },
  computed: {
    ...mapGetters(['actions'])
  },

  mounted () {
    // this.unique = this.actions.reduce((accumulator, current) => {
    //   if (accumulator.findIndex(object => object.id === current.id) === -1) {
    //     accumulator.push(current)
    //   }
    //   return accumulator
    // }, [])
  },

  methods: {
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
