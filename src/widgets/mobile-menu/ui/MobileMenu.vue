<script setup>
import { ref, onMounted } from "vue";
import { useMenuStore } from "@/entities";
import { Button } from "@/shared/ui";

const menu = useMenuStore();
const list = ref(null);

onMounted(() => {
  const items = list.value.querySelectorAll("li");
  items.forEach((item) => {
    item.addEventListener("click", () => {
      const block = document.querySelector(`#${item.dataset.scroll}`);
      menu.handleOpenMenu();
      window.scrollTo({
        top: block.offsetTop - 100,
        left: 0,
        behavior: "smooth",
      });
    });
  });
});
</script>

<template>
  <div class="mobile-menu" :class="menu.isActive ? 'active' : ''">
    <div class="mobile-menu-content">
      <nav ref="list">
        <ul>
          <li data-scroll="about">О лагере</li>
          <li data-scroll="house">Проживание</li>
          <li data-scroll="nutrition">Питание</li>
          <li data-scroll="rest">Досуг</li>
          <li data-scroll="documents">Документы</li>
          <li data-scroll="contacts">Контакты</li>
        </ul>
      </nav>
      <div class="info">
        <a href="tel:8 800 000-00-00" class="tel">8 800 000-00-00</a>
        <Button variable="outline">Личный кабинет</Button>
        <a href="#">Перейти на базу отдыха</a>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";
.mobile-menu.active {
  transform: translate(0);
  .mobile-menu-content {
    opacity: 1;
  }
}
.mobile-menu {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: var(--white-color);
  z-index: 90;
  transform: translate(-100%);
  transition: var(--trs-300);
  height: 100vh;

  .mobile-menu-content {
    padding: 110px 15px 100px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    // gap: 100px;
    height: 100%;
    opacity: 0;
    transition: var(--trs-300);
    transition-delay: 400ms;
    @media (max-height: 600px) {
      overflow: auto;
    }
    nav {
      ul {
        display: flex;
        align-items: center;
        flex-direction: column;
        gap: 35px;
        li {
          font-weight: 400;
          font-size: 22px;
          line-height: 26px;
          cursor: pointer;
        }
      }
    }
    .info {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 24px;
      .tel {
        font-weight: 500;
        font-size: 32px;
        line-height: 43px;
      }
      button {
        width: 100%;
        height: 58px;
        font-weight: 500;
        font-size: 22px;
        line-height: 26px;
      }
      a {
        &:last-child {
          margin-top: 10px;
          color: var(--rose-color);
          font-weight: 400;
          font-size: 22px;
          line-height: 26px;
        }
      }
    }
  }
}
</style>
