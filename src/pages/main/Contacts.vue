<script setup>
import { Map } from "@/entities";
</script>

<template>
  <div id="contacts" class="contacts">
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
@import "@/shared/styles/vars";

.contacts {
  position: relative;
  z-index: 2;
  padding-top: 140px;
  @media (max-width: $tab) {
    padding-top: 85px;
    &:after {
      display: none;
    }
  }

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
    @media (max-width: $tab) {
      grid-template-columns: repeat(1, 1fr);
    }
    .left {
      display: flex;
      flex-direction: column;
      padding-top: 30px;
      h3 {
        font-weight: 700;
        font-size: 60px;
        line-height: 66px;
        margin-bottom: 42px;
        @media (max-width: $tab) {
          font-size: 40px;
          line-height: 44px;
          margin-bottom: 66px;
        }
      }
      .address {
        margin-bottom: 40px;
        @media (max-width: $tab) {
          margin-bottom: 25px;
        }
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
          @media (max-width: $tab) {
            font-size: 18px;
            line-height: 25px;
          }
        }
      }
      .email {
        font-weight: 400;
        font-size: 20px;
        line-height: 23px;
        color: var(--rose-color);
        margin-bottom: 25px;
        @media (max-width: $tab) {
          font-size: 18px;
          line-height: 25px;
        }
      }
      .tel {
        margin-bottom: 25px;
        a {
          font-weight: 700;
          font-size: 32px;
          line-height: 35px;
          @media (max-width: $tab) {
            font-size: 28px;
            line-height: 39px;
          }
        }
        p {
          font-weight: 400;
          font-size: 20px;
          line-height: 28px;
          @media (max-width: $tab) {
            font-size: 18px;
            line-height: 25px;
          }
        }
      }
    }
    .right {
      @media (max-width: $tab) {
        height: 50vh;
        margin: 0 -15px;
      }
    }
  }
}
</style>
