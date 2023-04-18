<template>
  <footer>
    <div class="w-10/12 mx-auto py-10 grid lg:grid-cols-9 md:grid-cols-9 grid-cols-1 gap-10">
      <div class="contact col-span-3">
        <img src="../assets/LogoWhite.png" alt="">

        <div class="my-10">
          <span>Оставайтесь на связи</span>
          <div class="flex mt-5 space-x-5">
            <div class="flex items-center space-x-3">
              <img src="../assets/phone.svg" alt="">
              <a href="#">8 (495) 540-52-62</a>
            </div>
            <div class="flex items-center space-x-3">
              <img src="../assets/mail.svg" alt="">
              <a href="#">info@rosturplast.ru</a>
            </div>
          </div>
          <span class="block mt-3">Следите за новинками и акциями</span>
        </div>
        
        <div class="flex items-center space-x-5">
          <a href="#">
            <img src="../assets/vk.svg" alt="">
          </a>
          <a href="#">
            <img src="../assets/ok.svg" alt="">
          </a>
          <a href="#">
            <img src="../assets/tg.svg" alt="">
          </a>
        </div>

        <span class="cop-text block mt-20">©2000 - 2023  |   Все права защищены</span>
      </div>
      <div class="menu col-span-4 flex flex-col justify-between">
        <div>
          <h5 class="title">Компания</h5>
          <div class="flex justify-between mt-5">
            <div>
              <ul>
                <li>
                  <a href="#">О компании</a>
                </li>
                <li>
                  <a href="#">Каталог</a>
                </li>
                <li>
                  <a href="#">О компании</a>
                </li>
                <li>
                  <a href="#">Услуги</a>
                </li>
                <li>
                  <a href="#">Оплата</a>
                </li>
                <li>
                  <a href="#">Корзина</a>
                </li>
              </ul>
            </div>
            <div>
              <ul>
                <li>
                  <a href="#">Сервис и доставка</a>
                </li>
                <li>
                  <a href="#">Оформление заказа</a>
                </li>
                <li>
                  <a href="#">Контакты</a>
                </li>
              </ul>
            </div>
          </div>
        </div>

        <div class="flex space-x-10">
          <img src="../assets/mir.png" alt="">
          <img src="../assets/master.png" alt="">
          <img src="../assets/visa.png" alt="">
          <img src="../assets/unionpay.png" alt="">
        </div>
      </div>
      <div class="third col-span-2 flex items-end">
        <a href="#">Политика конфеденциальности</a>
      </div>
    </div>
    <div class="cookie py-5 border-t border-gray-100 flex flex-wrap justify-center items-center space-x-3 px-5">
      <span class="text-sm font-bold text-white text-center">Мы используем файлы cookie для вашего удобства пользования сайтом и повышения качества рекомендаций.</span>
      <a href="#" class="text-blue-500 text-sm font-bold">Подробнее</a>
      <button @click="deleteDiv" type="button" class="border border-gray-400 text-gray-400 text-sm font-bold py-2 px-4 rounded">Я согласен</button>
    </div>
  </footer>
</template>

<script>
import {onMounted, ref} from "vue";

export default {
  setup() {
    const divDeleted = ref(localStorage.getItem('divDeleted'));

    const deleteDiv = () => {
      document.querySelector('.cookie').remove();

      localStorage.setItem('divDeleted', true);

      divDeleted.value = true;
    }

    onMounted(() => {
      if (divDeleted.value) {
        document.querySelector('.cookie').remove();
      }
    });

    return {
      deleteDiv
    }
  }
}
</script>

<style scoped>
  footer {
    background-color: #42474D;
  }
  footer .contact .my-10 .mt-5 a:first-child, footer .contact .my-10 .mt-5 a:last-child {
    font-weight: 500;
    font-size: 12px;
    line-height: 24px;
    text-align: center;
    color: #FFFFFF;
  }
  footer .contact .my-10 span:first-child {
    font-weight: 700;
    font-size: 13px;
    line-height: 21px;
    color: #FFFFFF;
    padding-bottom: 10px;
    border-bottom: 1px solid #828D99;
  }
  footer .contact .my-10 span:last-child {
    font-weight: 400;
    font-size: 13px;
    line-height: 18px;
    color: #FFFFFF;
  }
  footer .contact .cop-text {
    font-weight: 400;
    font-size: 12px;
    line-height: 21px;
    color: #C3D3E5;
  }

  footer .menu h5.title {
    font-weight: 700;
    font-size: 18px;
    line-height: 21px;
    color: #FFFFFF;
    border-bottom: 1px solid #828D99;
    padding-bottom: 10px;
  }
  footer .menu ul li a {
    font-weight: 400;
    font-size: 16px;
    line-height: 13px;
    color: #FFFFFF;
    display: block;
    padding-bottom: 20px;
  }
  footer .third a {
    font-weight: 400;
    font-size: 12px;
    line-height: 21px;

    color: #C3D3E5;
  }
</style>