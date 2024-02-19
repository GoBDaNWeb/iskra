<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination } from "swiper/modules";
import { ref } from "vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

import { ArrowLeftIcon, ArrowRightIcon } from "@/shared/icons";
import DirectionCard from "./DirectionCard.vue";

import img1 from "@/shared/assets/images/direction/1.jpg";
import img2 from "@/shared/assets/images/direction/2.jpg";
import img3 from "@/shared/assets/images/direction/3.jpg";

import img4 from "@/shared/assets/images/direction/4.jpg";
import img5 from "@/shared/assets/images/direction/5.jpg";
import img6 from "@/shared/assets/images/direction/6.jpg";
import img7 from "@/shared/assets/images/direction/7.jpg";
import img8 from "@/shared/assets/images/direction/8.jpg";
import img9 from "@/shared/assets/images/direction/9.jpg";
import img10 from "@/shared/assets/images/direction/10.jpg";
import img11 from "@/shared/assets/images/direction/11.jpg";
import img12 from "@/shared/assets/images/direction/12.jpg";
import img13 from "@/shared/assets/images/direction/13.jpg";
import img14 from "@/shared/assets/images/direction/14.jpg";
import img15 from "@/shared/assets/images/direction/15.jpg";

const modules = ref([Navigation, Pagination]);
const prev = ref(null);
const next = ref(null);
const pagination = ref(null);

const directionList = [
  {
    id: 1,
    title: "Пост 1",
    imgs: [img1, img2, img3],
    text: "Участники направления «Пост 1» изучают опыт функционирования мемориальных объектов Вахты Памяти в различных регионах, основные правила создания и презентации патриотических документальных фильмов, осваивают алгоритмы создания патриотических проектов.",
    skills: [
      "дети научатся действовать быстро и синхронно",
      "принимать правильные решения в нестандартных ситуациях",
    ],
    textDirection: "right",
  },
  {
    id: 2,
    title: "Хранители истории",
    imgs: [img4, img5, img6],
    text: "Среди участников направления «Хранители истории» проводится большая работа по подготовке экскурсоводов в «Музее воинской славы» и «Партизанская деревня».",
    skills: [
      "использование природных источников для поддержания жизнедеятельности",
      "ориентирование в природных условиях в отсутствие специальных средств связи",
      "необходимые качества для подготовки к службе в рядах Российской Армии",
    ],
    textDirection: "left",
  },
  {
    id: 3,
    title: "Робототехника",
    imgs: [img7, img8, img9],
    text: "Наша программа предназначена для юных ученых и изобретателей. Участники курса познакомятся с основами робототехники, изучат принципы программирования и механики, а также получат уникальный опыт сборки",
    skills: [
      "практические навыки в области робототехники и программирования",
      "понимание того, как технологии могут изменять мир вокруг нас",
      "работа в команде над реальными проектами",
    ],
    textDirection: "right",
  },
  {
    id: 4,
    title: "Медиа победы",
    imgs: [img10, img11, img12],
    text: "Участники получают навыки репортажа, а так же учатся, как правильно брать интервью. Готовят и выпускают радиоэфиры, где рассказывают о жизни в лагере, об интересных фактах из жизни вожатых и творческих способностях детей. ",
    skills: [
      "понимание жанров кино, правильное изложение своих мыслей",
      "знание особенностей документального кино, его видах, принципах и приёмах",
      "техника создания сценария патриотического фильма",
    ],
    textDirection: "left",
  },
  {
    id: 5,
    title: "Защитники",
    imgs: [img13, img14, img15],
    text: "Участники направления учатся проводить мероприятия различного уровня, связанные с героическими событиями нашей истории и направленные на формирование патриотизма. ",
    skills: [
      "формы проведения акций «Георгиевская лента», «Свеча памяти», «Бессмертный полк»",
      "искусство театрального мастерства",
      "техника создания сценария патриотического фильма",
      "парашютная подготовка",
      "высотная подготовка",
    ],
    textDirection: "right",
  },
];
</script>

<template>
  <div class="direction-swiper">
    <div class="navigation">
      <button ref="prev" variant="clear"><ArrowLeftIcon /></button>
      <button ref="next" variant="clear"><ArrowRightIcon /></button>
    </div>
    <Swiper
      :pagination="{
        el: pagination,
        clickable: true,
      }"
      :slidesPerView="1.15"
      :spaceBetween="30"
      :navigation="{
        prevEl: prev,
        nextEl: next,
      }"
      :modules="modules"
      class="swiper-direction"
    >
      <SwiperSlide v-for="item in directionList" :key="item.id">
        <DirectionCard
          :title="item.title"
          :imgs="item.imgs"
          :text="item.text"
          :textDirection="item.textDirection"
          :skills="item.skills"
        />
      </SwiperSlide>
    </Swiper>
    <div ref="pagination" class="pagination"></div>
  </div>
</template>

<style lang="scss">
.direction-swiper {
  .pagination {
    display: flex;
    justify-content: center;
    margin-top: 25px;
    .swiper-pagination-bullet {
      width: 15px;
      height: 15px;
      background: var(--white-color) !important;
      opacity: 1;
    }
    .swiper-pagination-bullet-active {
      background: var(--purple-color) !important;
    }
  }
}
</style>
<style lang="scss" scoped>
.direction-swiper {
  position: relative;
  .swiper-direction {
    overflow: visible;
    .swiper-slide {
      opacity: 0.4;
      transition: var(--trs-300);
    }
    .swiper-slide-active {
      opacity: 1;
    }
  }
  .navigation {
    pointer-events: none;
    z-index: 2;
    position: absolute;
    width: 100%;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: auto;
    button {
      pointer-events: all;
      position: absolute;
      display: flex;
      align-items: center;
      justify-content: center;
      width: 36px;
      height: 36px;
      border-radius: 999px;
      background: var(--white-color);
      svg {
        stroke: var(--purple-color);
      }
      &:first-child {
        left: -40px;
      }
      &:last-child {
        right: -40px;
      }
    }
  }
}
</style>
