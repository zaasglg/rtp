<template>
  <div class="catalog">
    <div class="breadcrumb w-10/12 mx-auto flex items-center mt-10 space-x-3">
      <span>Главная</span>
      <svg width="8" height="12" viewBox="0 0 8 12" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M0.29303 1.70703L4.58603 6.00003L0.29303 10.293L1.70703 11.707L7.41403 6.00003L1.70703 0.293031L0.29303 1.70703Z" fill="#A6ACB3"/>
      </svg>
      <span>
        Каталог
      </span>
      <svg width="8" height="12" viewBox="0 0 8 12" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M4.93955 5.64648L1.00011 1.70703L1.707 1.00014L6.70689 6.00003L1.707 10.9999L1.00011 10.293L4.93955 6.35358L5.29311 6.00003L4.93955 5.64648Z" fill="#224386" stroke="#224386"/>
      </svg>
      <span>
        Трубы и фитинги из полипропилена
      </span>
    </div>

    <div class="w-10/12 mx-auto mt-10">
      <div class="grid lg:grid-cols-11 md:grid-cols-11 grid-cols-2 lg:gap-x-5 md:gap-x-5 gap-x-0 lg:gap-y-0 md:gap-y-0 gap-y-10">
        <div class="col-span-3">
          <div class="flex justify-between items-center">
            <span class="font-bold">Фильтр</span>
            <span class="font-thin text-gray-600">очистить</span>
          </div>

          <div class="flex items-center gap-2 mt-5">
            <input type="text" placeholder="от" v-model="data[0]" class="py-2 px-3 w-full bg-gray-100 border-2 border-gray-200 rounded outline-none" readonly>
            <span>-</span>
            <input type="text" placeholder="до" v-model="data[1]" class="py-2 px-3 w-full bg-gray-100 border-2 border-gray-200  rounded outline-none" readonly>
          </div>

          <div class="mt-5">
            <vue-slider v-model="data" height="6px" />
          </div>

          <div class="flex flex-col mt-10">

            <div class="inline-flex items-center" v-for="i in fitings">
              <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                    <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                  </svg>
                </div>
              </label>
              <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                {{ i  }}
              </label>
            </div>

          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Вид фитинга</span>
              <button @click="fistVisible = !fistVisible">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" v-if="fistVisible">
                  <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
                <svg width="10" height="6" viewBox="0 0 10 6" fill="none" xmlns="http://www.w3.org/2000/svg" v-else>
                  <path d="M1 1L5 5L9 1" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </button>
            </div>

            <transition name="collapse">
              <div class="flex flex-col mt-3" v-if="fistVisible">
                <div class="inline-flex items-center" v-for="i in type_fitings">
                  <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                    <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                    <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                      </svg>
                    </div>
                  </label>
                  <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                    {{ i }}
                  </label>
                </div>
              </div>
            </transition>

            <button @click="fistVisible = !fistVisible" class="text-sm text-color-main mt-2">{{ fistVisible ? "Скрыть часть" : "Показать часть" }}</button>
          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Тип фитинга</span>
              <button @click="secondVisible = !secondVisible">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" v-if="secondVisible">
                  <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
                <svg width="10" height="6" viewBox="0 0 10 6" fill="none" xmlns="http://www.w3.org/2000/svg" v-else>
                  <path d="M1 1L5 5L9 1" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </button>
            </div>


            <transition name="collapse">
              <div class="flex flex-col mt-3" v-if="secondVisible">
                <div class="inline-flex items-center">
                  <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                    <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                    <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                      </svg>
                    </div>
                  </label>
                  <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                    Переходной (21)
                  </label>
                </div>
              </div>
            </transition>

          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Тип соединения изделий</span>
              <button @click="thirdVisible = !thirdVisible">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" v-if="thirdVisible">
                  <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
                <svg width="10" height="6" viewBox="0 0 10 6" fill="none" xmlns="http://www.w3.org/2000/svg" v-else>
                  <path d="M1 1L5 5L9 1" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </button>
            </div>

            <transition name="collapse">
              <div class="flex flex-col mt-3" v-if="thirdVisible">
                <div class="inline-flex items-center">
                  <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                    <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                    <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                      </svg>
                    </div>
                  </label>
                  <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                    Разъемный  (1)
                  </label>
                </div>
                <div class="inline-flex items-center">
                  <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                    <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                    <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                      </svg>
                    </div>
                  </label>
                  <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                    Пайка (1)
                  </label>
                </div>
              </div>
            </transition>


          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Вид резьбы</span>
              <button @click="fourthVisible = !fourthVisible">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" v-if="fourthVisible">
                  <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
                <svg width="10" height="6" viewBox="0 0 10 6" fill="none" xmlns="http://www.w3.org/2000/svg" v-else>
                  <path d="M1 1L5 5L9 1" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </button>
            </div>

            <transition name="collapse">
              <div class="flex flex-col mt-3" v-if="fourthVisible">
                <div class="inline-flex items-center">
                  <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                    <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                    <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                      </svg>
                    </div>
                  </label>
                  <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                    Внутренняя (21)
                  </label>
                </div>
                <div class="inline-flex items-center">
                  <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                    <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                    <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                      </svg>
                    </div>
                  </label>
                  <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                    Наружная (60)
                  </label>
                </div>
                <div class="inline-flex items-center">
                  <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                    <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                    <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                      </svg>
                    </div>
                  </label>
                  <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                    Без резьбы (1)
                  </label>
                </div>
              </div>
            </transition>

          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Размер резьбы</span>
              <button @click="fifthVisible = !fifthVisible">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" v-if="fifthVisible">
                  <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
                <svg width="10" height="6" viewBox="0 0 10 6" fill="none" xmlns="http://www.w3.org/2000/svg" v-else>
                  <path d="M1 1L5 5L9 1" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </button>
            </div>


            <transition name="collapse">
              <div class="flex flex-col mt-3" v-if="fifthVisible">
                <div class="inline-flex items-center" v-for="i in size">
                  <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                    <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                    <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                      </svg>
                    </div>
                  </label>
                  <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                    {{ i }}
                  </label>
                </div>
              </div>
            </transition>

            <button @click="fifthVisible = !fifthVisible" class="text-sm text-color-main mt-2">{{ fifthVisible ? "Скрыть часть" : "Показать часть" }}</button>



          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Диаметр</span>
              <button @click="sixthVisible = !sixthVisible">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" v-if="sixthVisible">
                  <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
                <svg width="10" height="6" viewBox="0 0 10 6" fill="none" xmlns="http://www.w3.org/2000/svg" v-else>
                  <path d="M1 1L5 5L9 1" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </button>
            </div>

            <transition name="collapse">
              <div class="flex flex-col mt-3" v-if="sixthVisible">
                <div class="inline-flex items-center" v-for="i in diametr">
                  <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                    <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                    <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                      </svg>
                    </div>
                  </label>
                  <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                    {{ i }}
                  </label>
                </div>
              </div>
            </transition>

            <button @click="sixthVisible = !sixthVisible" class="text-sm text-color-main mt-2">{{ sixthVisible ? "Скрыть часть" : "Показать часть" }}</button>

          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Цвет</span>
              <button @click="eightsVisible = !eightsVisible">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" v-if="eightsVisible">
                  <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
                <svg width="10" height="6" viewBox="0 0 10 6" fill="none" xmlns="http://www.w3.org/2000/svg" v-else>
                  <path d="M1 1L5 5L9 1" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </button>
            </div>

            <transition name="collapse">
              <div class="flex flex-col mt-3" v-if="eightsVisible">
                <div class="inline-flex items-center">
                  <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                    <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                    <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                      </svg>
                    </div>
                  </label>
                  <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                    Белый (21)
                  </label>
                </div>
                <div class="inline-flex items-center">
                  <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                    <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                    <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                      </svg>
                    </div>
                  </label>
                  <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                    Серый (60)
                  </label>
                </div>
                <div class="inline-flex items-center">
                  <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                    <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                    <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                      </svg>
                    </div>
                  </label>
                  <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                    Зелёный (1)
                  </label>
                </div>
              </div>
            </transition>

            <button @click="eightsVisible = !eightsVisible" class="text-sm text-color-main mt-2">{{ eightsVisible ? "Скрыть часть" : "Показать часть" }}</button>


          </div>

          <div class="mt-10">
            <a href="#" class="block rounded py-3 px-4 text-white font-bold mt-2 text-center" style="background: #224386;">Применить</a>
          </div>

        </div>


        <div class="col-span-8">

          <div class="banner rounded-lg p-10">
            <div class="inline-block">
              <div class="bg-white rounded-full py-2 px-3 flex items-center space-x-3 w-full">
                <img src="../assets/system/logo1.svg" alt="">
                <span class="text-black" style="color: black; font-size: 25px;">ALPHA</span>
              </div>
            </div>

            <h2 class="text-white text-3xl font-bold mt-5">
              Трубы и фитинги <br>
              из  полипропилена
            </h2>
            <p class="w-7/12 block mt-5 text-gray-100 text-sm">
              Трубы из полипропилена для напорного водоснабжения (ХВС, ГВС) и отопления. Обладают отличными прочностными характеристиками и изготавливаются согласно требованиям ГОСТ. RTP располагает самым широким ассортиментом труб и фитингов, что позволяет осуществлять монтаж любой сложности.
            </p>
          </div>

          <div class="mt-10 flex items-center">
            <app-tabs :tabList="tabList">
              <template v-slot:tabPanel-1>
                <CatalogList />
              </template>
              <template v-slot:tabPanel-2>
                <CatalogList />
              </template>
              <template v-slot:tabPanel-3>
                <CatalogList />
              </template>
              <template v-slot:tabPanel-4>
                <CatalogList />
              </template>
            </app-tabs>
          </div>



        </div>
      </div>

    </div>

    <FooterWhite />
  </div>
</template>

<script>
import { ref } from 'vue'
import FooterWhite from "@/components/FooterWhite";
import AppTabs from "@/components/AppTabs";
import CatalogList from "@/components/CatalogList";

import VueSlider from 'vue-slider-component'
import 'vue-slider-component/theme/antd.css'

export default {
  components: {FooterWhite, AppTabs, CatalogList, VueSlider},
  setup() {
    const fitings = ["ФИТИНГИ", "Запорная арматура", "Коллекторы", "Труба армированная", "Труба не армированная", "Оборудование для монтажа", "Материалы для монтажа", "Другое"]
    const type_fitings = ["Муфта (21)", "Отводы и угольники (60)", "Тройники и крестовины (1)", "Запорная арматура (1)", "Другое (1)"]
    const size = ["1/2 (1)", "3/4 (1)", "1 (1)", "1,25 (1)", "1,5 (1)", "2 (1)", "3 (1)", "4 (1)"]
    const diametr = ["20 мм (60)", "25 мм (1)", "32 мм (1)", "40 мм (1)", "50 мм(1)", "63 мм (1)", "75 мм (1)", "90 мм (1)", "110 мм (1)", "125 мм(1)", "140 мм (1)", "160 мм(1)"]

    const tabList = ["По популярности", "Новинки", "Сначала дешёвые", "Сначала дорогие"]

    const data = ref([0, 20])


    const fistVisible = ref(true)
    const secondVisible = ref(true)
    const thirdVisible = ref(true)
    const fourthVisible = ref(true)

    const fifthVisible = ref(true)
    const sixthVisible = ref(true)
    const eightsVisible = ref(true)

    const sliderMin = ref(0);
    const sliderMax = ref(200);

    return {
      fitings,
      type_fitings,
      size,
      diametr,
      sliderMin,
      sliderMax,
      tabList,
      data,

      fistVisible,
      secondVisible,
      thirdVisible,
      fourthVisible,
      fifthVisible,
      sixthVisible,
      eightsVisible,
    }
  }
}
</script>

<style scoped>

  .catalog {
    background-color: #F5F5F5;
  }
  .breadcrumb span:first-child, .breadcrumb span:nth-child(3) {
    font-weight: 500;
    font-size: 15px;
    line-height: 21px;
    color: #A6ACB3;
  }
  .breadcrumb span:last-child {
    font-weight: 500;
    font-size: 15px;
    line-height: 21px;
    color: #224386;
  }
  .banner {
    background-image: url("../assets/banner.jpg");
    background-size: cover;
  }

  .collapse-enter-active,
  .collapse-leave-active {
    transition: opacity 0.2s ease;
  }

  .collapse-enter-from,
  .collapse-leave-to {
    opacity: 0;
  }

</style>