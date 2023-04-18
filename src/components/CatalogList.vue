<template>
  <div class="catalog-list mt-10">
    <div v-for="i in 3" class="bg-white p-3 grid lg:grid-cols-9 md:grid-cols-9 grid-cols-2 my-10 gap-5">
      <div style="width: 274px; height: 216px" class="bg-gray-100 col-span-3 flex items-center justify-center border-2 border-gray-200">
        <img src="../assets/picture.svg" alt="">
      </div>
      <div class="col-span-6">
        <h2 class="font-bold">Труба из полипропилена PN SDR 11 - 20*1.9мм</h2>
        <span class="text-sm text-gray-700 leading-4 block mt-2">Труба из полипропилена PN SDR 11 для холодной воды, проекта сантехники для дома ALPHA, 4 метра - 20*1.9мм.</span>
        <div class="mt-3 flex justify-between">
          <div>
            <ul>
              <li class="text-gray-500 text-sm font-medium">DN номинальный диаметр, мм: <span class="text-gray-900"> 20</span></li>
              <li class="text-gray-500 text-sm font-medium">Толщина стенок, мм: <span class="text-gray-900"> 1,9</span></li>
              <li class="text-gray-500 text-sm font-medium">Кол-во в упаковке м/шт: <span class="text-gray-900"> 100/25</span></li>
              <li class="text-gray-500 text-sm font-medium">Материал: <span class="text-gray-900"> Полипропилен</span> </li>
              <li class="text-gray-500 text-sm font-medium">Цвет: <span class="text-gray-900"> Белый</span></li>
            </ul>
          </div>
          <div>
            <span class="font-bold text-lg">2 885 ₽</span>
            <AppCount />
            <a href="#" class="block rounded py-3 px-4 text-white font-bold mt-2" style="background: #224386;">В корзину</a>
          </div>
        </div>
      </div>
    </div>
    <div class="rounded grid lg:grid-cols-7 md:grid-cols-7 grid-cols-1 gap-5 items-center" style="background: linear-gradient(90deg, #224386 20.72%, rgba(34, 67, 134, 0.8) 47.74%, #82D3FC 98.28%);">
      <div class="col-span-2">
        <svg width="238" height="170" viewBox="0 0 238 170" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M111.303 101.725C112.77 110.54 113.08 121.628 125.417 121.628H196.675C208.353 121.628 208.821 111.932 210.866 103.733L225.828 43.8887H101.662L111.303 101.725Z" fill="#2598D2"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M163.505 69.1577C153.54 86.4169 147.259 104.414 144.529 121.625H196.677C208.355 121.625 208.823 111.93 210.867 103.731L225.829 43.8862H181.491C174.923 51.4304 168.855 59.8869 163.503 69.1577H163.505Z" fill="#76CCF7"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M183.875 143.905C176.927 143.905 171.287 149.543 171.287 156.493C171.287 163.442 176.925 169.078 183.875 169.078C190.824 169.078 196.458 163.44 196.458 156.493C196.46 149.543 190.819 143.905 183.875 143.905Z" fill="#FAFEFF"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M135.659 143.905C128.712 143.905 123.071 149.543 123.071 156.493C123.071 163.44 128.709 169.078 135.659 169.078C142.608 169.078 148.245 163.44 148.245 156.493C148.245 149.543 142.608 143.905 135.659 143.905Z" fill="#FAFEFF"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M232.636 32.4133H101.151L97.6141 6.15072C97.103 2.34639 94.9824 0.712891 91.2186 0.712891H65.2928C61.8156 0.712891 59 3.53569 59 7.01046C59 10.4852 61.8132 13.3033 65.2928 13.3033H85.8166L100.52 102.785C102.971 118.186 106.498 133.103 126.513 133.103H195.736C216.005 133.103 218.233 118.638 221.87 104.082L237.312 42.3146C238.506 37.5406 238.8 32.4133 232.636 32.4133ZM220.076 60.9159H134.413C130.95 60.9159 128.12 63.7459 128.12 67.2087C128.12 70.6739 130.95 73.5039 134.413 73.5039H216.931L213.339 87.8734H149.8C146.34 87.8734 143.51 90.7034 143.51 94.1662V94.171C143.51 97.6314 146.34 100.461 149.8 100.461H210.189L209.523 103.134C207.534 111.096 207.08 120.517 195.736 120.517H126.513C114.529 120.517 114.229 109.747 112.803 101.183L103.439 44.9989H224.057L220.076 60.9159Z" fill="#FAFEFF"/>
          <rect x="15" y="30" width="54" height="13" rx="6.5" fill="white"/>
          <rect y="53" width="79" height="13" rx="6.5" fill="white"/>
          <rect x="45" y="76" width="38" height="13" rx="6.5" fill="white"/>
        </svg>
      </div>
      <div class="col-span-3">
        <h2 class="text-white font-medium text-2xl">Соберите мне корзину</h2>
        <p class="text-white text-sm text-gray-100 mt-2">Доверти покупки профессионалам, загрузите или заполните список и наш менеджер соберет вам корзину </p>
      </div>
      <div class="col-span-2 pr-5">
        <a href="#" class="block rounded py-3 px-4 text-white text-sm mt-2" style="background: #224386;">Заказать обратный звонок</a>
      </div>

    </div>
    <div v-for="i in 6" class="bg-white p-3 grid lg:grid-cols-9 md:grid-cols-9 grid-cols-2 my-10 gap-5">
      <div style="width: 274px; height: 216px" class="bg-gray-100 col-span-3 flex items-center justify-center border-2 border-gray-200">
        <img src="../assets/picture.svg" alt="">
      </div>
      <div class="col-span-6">
        <h2 class="font-bold">Труба из полипропилена PN SDR 11 - 20*1.9мм</h2>
        <span class="text-sm text-gray-700 leading-4 block mt-2">Труба из полипропилена PN SDR 11 для холодной воды, проекта сантехники для дома ALPHA, 4 метра - 20*1.9мм.</span>
        <div class="mt-3 flex justify-between">
          <div>
            <ul>
              <li class="text-gray-500 text-sm font-medium">DN номинальный диаметр, мм: <span class="text-gray-900"> 20</span></li>
              <li class="text-gray-500 text-sm font-medium">Толщина стенок, мм: <span class="text-gray-900"> 1,9</span></li>
              <li class="text-gray-500 text-sm font-medium">Кол-во в упаковке м/шт: <span class="text-gray-900"> 100/25</span></li>
              <li class="text-gray-500 text-sm font-medium">Материал: <span class="text-gray-900"> Полипропилен</span> </li>
              <li class="text-gray-500 text-sm font-medium">Цвет: <span class="text-gray-900"> Белый</span></li>
            </ul>
          </div>
          <div>
            <span class="font-bold text-lg">2 885 ₽</span>
            <AppCount />
            <a href="#" class="block rounded py-3 px-4 text-white font-bold mt-2" style="background: #224386;">В корзину</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AppCount from "@/components/AppCount";

export default {
  name: "CatalogList",
  components: {AppCount}
}
</script>

<style scoped>

</style>