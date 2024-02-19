<script setup></script>

<template>
  <footer>
    <div class="container">
      <div class="footer-inner">
        <div class="top">
          <div class="logo">
            <img src="@/shared/assets/images/logo-white.png" alt="logo" />
          </div>
          <div class="politic">
            <a href="#">Политика конфиденциальности</a>
            <a href="#">Политика обработки персональных данных</a>
          </div>
        </div>
        <div class="bottom">
          <p>© ... Все права защищены</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
footer {
  background: var(--purple-color);
  position: relative;
  z-index: 1;
  padding-top: 90px;
  padding-bottom: 22px;
  .footer-inner {
    display: flex;
    flex-direction: column;
    gap: 40px;
    .top {
      display: flex;
      align-items: flex-start;
      gap: 60px;
      .logo {
        width: 128px;
        height: 27px;
        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
      .politic {
        display: flex;
        flex-direction: column;
        gap: 15px;
        a {
          font-weight: 400;
          font-size: 16px;
          color: var(--white-color);
          line-height: 22px;
        }
      }
    }
    .bottom p {
      font-weight: 400;
      font-size: 16px;
      line-height: 22px;
      opacity: 0.3;
      color: var(--white-color);
    }
  }
}
</style>
