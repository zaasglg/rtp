<template>
  <header>
    <nav>
      <div class="grid lg:grid-cols-5 md:grid-cols-5 grid-cols-1 w-10/12 mx-auto py-5 gap-10">
        <div class="logo flex items-center space-x-3">
          <router-link to="/"><img src="../assets/logo.svg" alt=""></router-link>
          <div class="line"></div>
          <span class="text-white text-left">Производитель <br>
          инженерной сантехники <br>
          с 17 летним опытом</span>
        </div>
        <div class="col-span-3">
          <div class="menu space-x-3">
            <a href="#">Системы</a>
            <a href="#">Услуги</a>
            <a href="#">Сервис и доставка</a>
            <a href="#">Оплата</a>
            <a href="#">О компании</a>
            <a href="#">Контакты</a>
          </div>
          <div class="contact flex items-center space-x-3 mt-5">
            <a href="#">8 (495) 540-52-62</a>
            <div></div>
            <span>Звонок бесплатный <br>Пн-Пт 9:00-18:00 </span>
          </div>
        </div>
        <div class="btn flex flex-col">
          <a href="#" class="px-3 py-2">
            Заказать обратный звонок
          </a>
          <a href="#" class="block mt-2">sales@rtp.ru</a>
        </div>
      </div>
    </nav>

    <div class="catalog w-10/12 mx-auto mt-5 grid lg:grid-cols-6 md:grid-cols-6 grid-cols-1 items-center gap-10">
      <div>
        <router-link to="/catalog" class="flex items-center space-x-3 py-2 px-3">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="white" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 6.75h12M8.25 12h12m-12 5.25h12M3.75 6.75h.007v.008H3.75V6.75zm.375 0a.375.375 0 11-.75 0 .375.375 0 01.75 0zM3.75 12h.007v.008H3.75V12zm.375 0a.375.375 0 11-.75 0 .375.375 0 01.75 0zm-.375 5.25h.007v.008H3.75v-.008zm.375 0a.375.375 0 11-.75 0 .375.375 0 01.75 0z" />
          </svg>
          <span>Каталог товаров</span>
        </router-link>
      </div>
      <div class="col-span-4">
        <input type="text" placeholder="Поиск" class="outline-none">
      </div>
      <div class="flex flex-col">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="#828D99" width="28px" height="28px">
          <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 00-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 00-16.536-1.84M7.5 14.25L5.106 5.272M6 20.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm12.75 0a.75.75 0 11-1.5 0 .75.75 0 011.5 0z" />
        </svg>
        <span>Корзина</span>
      </div>
    </div>
  </header>
</template>

<script>
export default {

}
</script>

<style scoped>
  header {
    background-color: #F5F5F5;
  }
  nav {
    background-color: #224386;
    border-radius: 100px;
  }
  .logo .line {
    width: 1px;
    height: 50px;
    background-color: #E0E0E0;
  }
  .logo span {
    font-style: normal;
    font-weight: 400;
    font-size: 12px;
  }
  .menu a {
    font-style: normal;
    font-weight: 400;
    font-size: 15px;

    color: #8CA7DD;
  }
  header .contact a {
    font-style: normal;
    font-weight: 700;
    font-size: 23px;
    text-align: center;
    color: #FFFFFF;
  }
  header .contact div {
    width: 1px;
    height: 25px;
    background-color: #E0E0E0;
  }
  header .contact span:last-child {
    font-style: normal;
    font-weight: 400;
    font-size: 10px;
    text-align: right;
    color: #FFFFFF;
  }
  .btn a:first-child {
    font-style: normal;
    font-weight: 400;
    font-size: 15px;
    line-height: 20px;
    color: #FFFFFF;
    border: 2px solid #FFFFFF;
    border-radius: 23px;
  }
  .btn a:last-child {
    font-style: normal;
    font-weight: 700;
    font-size: 24px;
    line-height: 28px;
    text-align: right;
    color: #FFFFFF;
  }


  /*catalog*/
  .catalog div:first-child a {
    background: #224386;
    border-radius: 3px;
  }
  .catalog div:first-child span {
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 18px;
    color: #FFFFFF;
  }
  .catalog div:nth-child(2) input {
    border: 2px solid #224386;
    border-radius: 29px;
    padding: 9px 36px;
    width: 100%;
  }

  .catalog div:last-child span {
    font-style: normal;
    font-weight: 400;
    font-size: 11px;
    color: #828D99;
  }
</style>