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
      window.scrollTo({
        top: block.offsetTop - 150,
        left: 0,
        behavior: "smooth",
      });
    });
  });
});
</script>

<template>
  <header>
    <div class="container">
      <div class="header-inner">
        <div class="logo">
          <img src="@/shared/assets/images/logo.png" alt="logo" />
        </div>
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
          <div class="left">
            <a href="tel:8 800 000-00-00">8 800 000-00-00</a>
          </div>
          <div class="right">
            <a href="#">Перейти на базу отдыха</a>
            <Button variable="outline">Личный кабинет</Button>
          </div>
        </div>
        <div
          class="burger"
          :class="menu.isActive ? 'active' : ''"
          @click="menu.handleOpenMenu"
        ></div>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";
header {
  background: var(--white-color);
  position: fixed;
  left: 0;
  z-index: 100;
  right: 0;
  .header-inner {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 60px;
    padding-bottom: 22px;
    position: relative;
    @media (max-width: $desktop-sm) {
      padding-top: 22px;
    }
    .logo {
      width: 156px;
      height: 32px;
      img {
        word-wrap: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    nav {
      @media (max-width: $desktop-sm) {
        display: none;
      }
      ul {
        display: flex;
        gap: 30px;
        li {
          cursor: pointer;
          font-size: 18px;
          line-height: 21px;
          font-weight: 400;
        }
      }
    }
    .info {
      display: flex;
      align-items: center;
      gap: 22px;
      @media (max-width: $desktop-sm) {
        display: none;
      }
      .left {
        a {
          font-weight: 500;
          font-size: 20px;
          line-height: 27px;
        }
      }
      .right {
        display: flex;
        flex-direction: column;
        gap: 11px;
        a {
          color: var(--rose-color);
          font-weight: 400;
          font-size: 18px;
          line-height: 21px;
          position: absolute;
          top: 25px;
          right: 0;
        }
        button {
          font-weight: 500;
          font-size: 18px;
          line-height: 22px;
          width: 205px;
        }
      }
    }
    .burger.active {
    }
    .burger.active {
      &:after {
        transform: rotate(45deg);
        top: 5px;
      }
      &:before {
        transform: rotate(-45deg);
        bottom: 5px;
      }
    }
    .burger {
      position: relative;
      height: 12px;
      width: 32px;
      cursor: pointer;
      display: none;

      @media (max-width: $desktop-sm) {
        display: block;
      }
      &:after {
        content: "";
        position: absolute;
        width: 100%;
        height: 2px;
        background: var(--black-color);
        top: 0;
        transition: var(--trs-300);
      }
      &:before {
        content: "";
        position: absolute;
        width: 100%;
        height: 2px;
        background: var(--black-color);
        bottom: 0;
        transition: var(--trs-300);
      }
    }
  }
}
</style>
