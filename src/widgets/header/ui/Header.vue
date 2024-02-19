<script setup>
import { Button } from "@/shared/ui";
</script>

<template>
  <header>
    <div class="container">
      <div class="header-inner">
        <div class="logo">
          <img src="@/shared/assets/images/logo.png" alt="logo" />
        </div>
        <nav>
          <ul>
            <li><a href="">О лагере</a></li>
            <li><a href="">Проживание</a></li>
            <li><a href="">Питание</a></li>
            <li><a href="">Досуг</a></li>
            <li><a href="">Документы</a></li>
            <li><a href="">Контакты</a></li>
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
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
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
      ul {
        display: flex;
        gap: 30px;
      }
    }
    .info {
      display: flex;
      align-items: center;
      gap: 22px;
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
  }
}
</style>
