<script setup>
import { Collapse } from "vue-collapsed";
import { reactive } from "vue";
const questions = reactive([
  {
    title: "Как доехать до лагеря?",
    answer:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis fuga nisi cum dignissimos, nemo veritatis odio minus dolor magni ipsum modi sed repellendus eius? Illo nihil aliquid perspiciatis eveniet placeat. Fugit voluptatum cupiditate a ipsa voluptas rerum nulla necessitatibus deserunt accusantium praesentium rem alias, itaque autem recusandae. Recusandae, magni ut.",
    isExpanded: false, // Initial value
  },
  {
    title: "Схема территории лагеря",
    answer:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis fuga nisi cum dignissimos, nemo veritatis odio minus dolor magni ipsum modi sed repellendus eius? Illo nihil aliquid perspiciatis eveniet placeat. Fugit voluptatum cupiditate a ipsa voluptas rerum nulla necessitatibus deserunt accusantium praesentium rem alias, itaque autem recusandae. Recusandae, magni ut.",
    isExpanded: false,
  },
  {
    title: "Можно ли приехать навестить ребенка? ",
    answer:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis fuga nisi cum dignissimos, nemo veritatis odio minus dolor magni ipsum modi sed repellendus eius? Illo nihil aliquid perspiciatis eveniet placeat. Fugit voluptatum cupiditate a ipsa voluptas rerum nulla necessitatibus deserunt accusantium praesentium rem alias, itaque autem recusandae. Recusandae, magni ut.",
    isExpanded: false,
  },
  {
    title: "Что я могу привезти ребенку из еды? ",
    answer:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis fuga nisi cum dignissimos, nemo veritatis odio minus dolor magni ipsum modi sed repellendus eius? Illo nihil aliquid perspiciatis eveniet placeat. Fugit voluptatum cupiditate a ipsa voluptas rerum nulla necessitatibus deserunt accusantium praesentium rem alias, itaque autem recusandae. Recusandae, magni ut.",
    isExpanded: false,
  },
  {
    title: "Как связаться с воспитателем отряда, в который попал мой ребёнок? ",
    answer:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis fuga nisi cum dignissimos, nemo veritatis odio minus dolor magni ipsum modi sed repellendus eius? Illo nihil aliquid perspiciatis eveniet placeat. Fugit voluptatum cupiditate a ipsa voluptas rerum nulla necessitatibus deserunt accusantium praesentium rem alias, itaque autem recusandae. Recusandae, magni ut.",
    isExpanded: false,
  },
  {
    title: "Где я смогу пообщаться с ребенком в часы посещения?",
    answer:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis fuga nisi cum dignissimos, nemo veritatis odio minus dolor magni ipsum modi sed repellendus eius? Illo nihil aliquid perspiciatis eveniet placeat. Fugit voluptatum cupiditate a ipsa voluptas rerum nulla necessitatibus deserunt accusantium praesentium rem alias, itaque autem recusandae. Recusandae, magni ut.",
    isExpanded: false,
  },
  {
    title: "Могу ли я забрать ребенка погулять?",
    answer:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis fuga nisi cum dignissimos, nemo veritatis odio minus dolor magni ipsum modi sed repellendus eius? Illo nihil aliquid perspiciatis eveniet placeat. Fugit voluptatum cupiditate a ipsa voluptas rerum nulla necessitatibus deserunt accusantium praesentium rem alias, itaque autem recusandae. Recusandae, magni ut.",
    isExpanded: false,
  },
  {
    title: "Где я могу посмотреть фотографии своего ребенка?",
    answer:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis fuga nisi cum dignissimos, nemo veritatis odio minus dolor magni ipsum modi sed repellendus eius? Illo nihil aliquid perspiciatis eveniet placeat. Fugit voluptatum cupiditate a ipsa voluptas rerum nulla necessitatibus deserunt accusantium praesentium rem alias, itaque autem recusandae. Recusandae, magni ut.",
    isExpanded: false,
  },
]);
const props = defineProps(["questions"]);

function handleAccordion(selectedIndex) {
  questions.forEach((_, index) => {
    questions[index].isExpanded =
      index === selectedIndex ? !questions[index].isExpanded : false;
  });
}
</script>

<template>
  <div
    class="accordion"
    :class="{ active: question.isExpanded }"
    v-for="(question, index) in questions"
    :key="question.title"
  >
    <button @click="() => handleAccordion(index)">
      <p>
        {{ question.title }}
      </p>
      <div class="icon"></div>
    </button>
    <Collapse :when="questions[index].isExpanded" class="collapse">
      <p>
        {{ question.answer }}
      </p>
    </Collapse>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.accordion.active {
  button {
    border-radius: 12px 12px 0 0;
    .icon {
      &:after {
        height: 0;
      }
    }
  }
  .collapse {
    background: var(--white-color);
    border-radius: 0 0 12px 12px;

    p {
      padding-top: 40px;
      padding-bottom: 70px;
      @media (max-width: $tab) {
        padding-top: 25px;
        padding-bottom: 25px;
      }
    }
  }
}
.accordion {
  width: 100%;
  button {
    width: 100%;
    background: var(--purple-color);
    padding: 15px 40px;
    border-radius: 12px;
    transition: var(--trs-300);
    display: flex;
    align-items: center;
    justify-content: space-between;
    p {
      text-align: left;
      color: var(--white-color);
      font-weight: 400;
      font-size: 24px;
      line-height: 36px;
      @media (max-width: $tab) {
        font-size: 20px;
        line-height: 28px;
      }
    }
    .icon {
      width: 33px;
      height: 33px;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      &:before {
        content: "";
        width: 33px;
        height: 3px;
        background: var(--white-color);
        position: absolute;
        top: 0;
        bottom: 0;
        margin: auto 0;
        display: block;
      }
      &:after {
        content: "";
        height: 33px;
        width: 3px;
        background: var(--white-color);
        position: absolute;
        right: 0;
        left: 0;
        margin: 0 auto;
        display: block;
        transition: var(--trs-300);
      }
    }
  }
  .collapse {
    background: var(--white-color);
    border-radius: 0 0 12px 12px;

    p {
      padding: 0 40px;
      transition: var(--trs-300);
      font-weight: 400;
      font-size: 20px;
      line-height: 28px;
      @media (max-width: $tab) {
        font-size: 16px;
        line-height: 22px;
        padding: 0 20px;
      }
    }
  }
}
</style>
