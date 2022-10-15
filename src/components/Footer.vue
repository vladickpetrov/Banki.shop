<template lang="">
  <footer class="footer">
    <div class="footer__container">
      <ul class="footer__links-container">
        <li class="footer__link"><a>Каталог</a></li>
        <li class="footer__link"><a>Доставка</a></li>
        <li class="footer__link"><a>Оплата</a></li>
        <li class="footer__link"><a>Контакты</a></li>
        <li class="footer__link"><a>О&nbspкомпании</a></li>
      </ul>
      <ul class="info">
        <li class="info__number">
          <div class="info__image-num"></div>
          +7 (812) 555-55-55
        </li>
        <li class="info__adress">
          <div class="info__image-adr"></div>
          г. Санкт-Петербург, ул. Ефимова, 3
        </li>
      </ul>
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style scoped>
.footer {
  background-color: #eceaea;
  min-height: 97px;
  width: 100%;
  display: flex;
  justify-content: center;
}

.footer__container {
  width: 1216px;
  display: flex;
  align-items: center;
}

.footer__links-container {
  display: flex;
  padding-right: 126px;
  padding-left: 96px;
}

.footer__link {
  padding-left: 48px;
  font-size: 14px;
  font-weight: 400;
  line-height: 36px;
}

.footer__link:first-child {
  padding-left: 0;
}

.info {
  display: flex;
}

.info__number,
.info__adress {
  height: 22px;
  display: flex;
  align-items: center;
  white-space: nowrap;
}

.info__number {
  padding-right: 51px;
  width: 100%;
}
.info__image-num,
.info__image-adr {
  padding-right: 8px;
  width: 16px;
  height: 16px;
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
}

.info__image-num {
  background-image: url(../images/phone.svg);
}

.info__image-adr {
  background-image: url(../images/adress.svg);
}

@media (max-width: 1430px) {
  .footer__links-container {
    padding-left: 0;
  }
}

@media (max-width: 1280px) {
  .info {
    flex-direction: column;
    gap: 10px;
    padding-right: 20px;
  }

  .footer__container {
    justify-content: space-between;
  }

  .footer__links-container {
    padding-left: 20px;
  }
}

@media (max-width: 1030px) {
  .footer__links-container {
    flex-direction: column;
    padding-right: 0;
    padding-left: 0;
  }

  .footer__link:first-child {
    padding-left: 48px;
  }

  .info__number {
    padding-right: 0;
  }

  .footer__container {
    padding-top: 20px;
    padding-bottom: 20px;
  }
}

@media (max-width: 580px) {
  .info {
    display: none;
  }
}
</style>
