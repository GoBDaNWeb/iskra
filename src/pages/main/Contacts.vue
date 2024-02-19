<script setup>
import { Map } from "@/entities";
</script>

<template>
  <div class="contacts">
    <div class="container">
      <div class="contacts-inner">
        <div class="left">
          <h3>Контакты</h3>
          <div class="address">
            <span>Адрес</span>
            <p>
              Московская область, г. Красногорск, <br />
              микрорайон Опалиха, база отдыха <br />
              и оздоровления детей (ДОЛ) «Искра»
            </p>
          </div>
          <a href="mailto:nisaeva@mggt.ru" class="email">nisaeva@mggt.ru</a>
          <a href="mailto:dol-iskra-mggt@mail.ru" class="email"
            >dol-iskra-mggt@mail.ru
          </a>
          <div class="tel">
            <a href="tel:8 (495) 984-97-65">8 (495) 984-97-65</a>
            <p>администратор</p>
          </div>
          <div class="tel">
            <a href="tel:8 (495) 984-97-61">8 (495) 984-97-61</a>
            <p>бухгалтер</p>
          </div>
        </div>
        <div class="right"><Map /></div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.contacts {
  position: relative;
  z-index: 2;
  padding-top: 140px;
  &:after {
    content: "";
    position: absolute;
    background: url("@/shared/assets/images/shapes/shape-contacts.svg");
    background-size: cover;
    background-repeat: no-repeat;
    bottom: -55px;
    width: 100%;
    height: 60px;
  }
  .contacts-inner {
    display: grid;
    grid-template-columns: calc(30% - 30px) calc(70% - 30px);
    gap: 60px;
    .left {
      display: flex;
      flex-direction: column;
      padding-top: 30px;
      h3 {
        font-weight: 700;
        font-size: 60px;
        line-height: 66px;
        margin-bottom: 42px;
      }
      .address {
        margin-bottom: 40px;
        span {
          font-weight: 700;
          font-size: 20px;
          line-height: 24px;
          color: var(--black-color);
        }
        p {
          margin-top: 10px;
          font-weight: 400;
          font-size: 20px;
          line-height: 28px;
          color: var(--black-color);
        }
      }
      .email {
        font-weight: 400;
        font-size: 20px;
        line-height: 23px;
        color: var(--rose-color);
        margin-bottom: 25px;
      }
      .tel {
        margin-bottom: 25px;
        a {
          font-weight: 700;
          font-size: 32px;
          line-height: 35px;
        }
        p {
          font-weight: 400;
          font-size: 20px;
          line-height: 28px;
        }
      }
    }
    .right {
    }
  }
}
</style>
