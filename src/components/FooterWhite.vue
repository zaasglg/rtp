<template>
  <footer>
    <div class="w-10/12 mx-auto py-10 grid lg:grid-cols-9 md:grid-cols-9 grid-cols-1 gap-10">
      <div class="contact col-span-3">
        <img src="../assets/logoBlack.png" alt="">

        <div class="my-10">
          <span>Оставайтесь на связи</span>
          <div class="flex mt-5 space-x-5">
            <div class="flex items-center space-x-3">
              <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M15.975 12.0939L15.2484 15.2439C15.1464 15.6892 14.755 16.0008 14.2966 16.0008C6.4125 16.0002 0 9.58768 0 1.70331C0 1.24518 0.311531 0.853308 0.756875 0.751746L3.90687 0.0251839C4.36562 -0.0811285 4.83437 0.156996 5.025 0.591433L6.47875 3.98206C6.64869 4.38143 6.53406 4.84674 6.19812 5.12112L4.51562 6.47205C5.5775 8.63518 7.33625 10.3939 9.5 11.4564L10.8775 9.77517C11.149 9.4383 11.6178 9.32174 12.0172 9.49471L15.4078 10.9481C15.8156 11.1627 16.0813 11.6377 15.975 12.0939Z" fill="#42474D"/>
              </svg>
              <a href="#">8 (495) 540-52-62</a>
            </div>
            <div class="flex items-center space-x-3">
              <svg width="16" height="12" viewBox="0 0 16 12" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M8 9C7.48344 9 6.96688 8.83056 6.52625 8.48719L0 3.4125V10.5C0 11.3281 0.671562 12 1.5 12H14.5C15.3284 12 16 11.3284 16 10.5V3.4125L9.475 8.49063C9.03438 8.83125 8.51562 9 8 9ZM0.509063 2.54063L7.14031 7.7C7.64625 8.09375 8.355 8.09375 8.86094 7.7L15.4922 2.54063C15.7844 2.29063 16 1.90625 16 1.5C16 0.671562 15.3281 0 14.5 0H1.5C0.671562 0 0 0.671562 0 1.5C0 1.90625 0.187813 2.29063 0.509063 2.54063Z" fill="#42474D"/>
              </svg>

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
    <div class="py-5 border-t border-gray-100 flex flex-wrap justify-center items-center space-x-3">
      <span class="text-sm font-bold text-center">Мы используем файлы cookie для вашего удобства пользования сайтом и повышения качества рекомендаций.</span>
      <a href="#" class="text-blue-500 text-sm font-bold">Подробнее</a>
      <button class="border border-gray-400 text-gray-400 text-sm font-bold py-2 px-4 rounded">Я согласен</button>
    </div>
  </footer>
</template>

<script>
export default {

}
</script>

<style scoped>
  footer {
    background-color: #FFFFFF;
  }
  footer .contact .my-10 .mt-5 a:first-child, footer .contact .my-10 .mt-5 a:last-child {
    font-weight: 500;
    font-size: 12px;
    line-height: 24px;
    text-align: center;
    color: #42474D;
  }
  footer .contact .my-10 span:first-child {
    font-weight: 700;
    font-size: 13px;
    line-height: 21px;
    color: #42474D;
    padding-bottom: 10px;
    border-bottom: 1px solid #828D99;
  }
  footer .contact .my-10 span:last-child {
    font-weight: 400;
    font-size: 13px;
    line-height: 18px;
    color: #42474D;
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
    color: #42474D;
    border-bottom: 1px solid #828D99;
    padding-bottom: 10px;
  }
  footer .menu ul li a {
    font-weight: 400;
    font-size: 16px;
    line-height: 13px;
    color: #42474D;
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