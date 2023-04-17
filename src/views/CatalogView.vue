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
            <input type="text" placeholder="от" v-model="sliderMin" class="py-2 px-3 w-full bg-gray-100 border-2 border-gray-200 rounded outline-none">
            <span>-</span>
            <input type="text" placeholder="до" v-model="sliderMax" class="py-2 px-3 w-full bg-gray-100 border-2 border-gray-200  rounded outline-none">
          </div>

          <div class="mt-5">
            <AppSlider :max="700" v-model:min-value="sliderMin" v-model:max-value="sliderMax"/>
          </div>

          <div class="flex flex-col">

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
              <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>

            <div class="flex flex-col mt-3">
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

            <a href="#" class="text-sm text-color-main mt-2">скрыть часть</a>
          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Тип фитинга</span>
              <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>

            <div class="flex flex-col mt-3">
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

          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Тип соединения изделий</span>
              <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>

            <div class="flex flex-col mt-3">
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

          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Вид резьбы</span>
              <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>

            <div class="flex flex-col mt-3">
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

          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Размер резьбы</span>
              <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>

            <div class="flex flex-col mt-3">
              <div class="inline-flex items-center" v-for="i in size.length">
                <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                  <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                  <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                      <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                    </svg>
                  </div>
                </label>
                <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                  {{ size[i-1] }}
                </label>
              </div>
            </div>

            <a href="#" class="text-sm text-color-main mt-2">скрыть часть</a>
          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Диаметр</span>
              <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>

            <div class="flex flex-col mt-3">
              <div class="inline-flex items-center" v-for="i in diametr.length">
                <label class="relative flex cursor-pointer items-center rounded-full p-3" data-ripple-dark="true">
                  <input type="checkbox" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-md border border-blue-gray-200 transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-12 before:w-12 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue-gray-500 before:opacity-0 before:transition-opacity checked:border-color-main checked:bg-color-main checked:before:bg-color-main hover:before:opacity-10"/>
                  <div class="pointer-events-none absolute top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 text-white opacity-0 transition-opacity peer-checked:opacity-100">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 20 20" fill="currentColor" stroke="currentColor" stroke-width="1">
                      <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                    </svg>
                  </div>
                </label>
                <label class="mt-px cursor-pointer select-none font-bold text-gray-700">
                  {{ diametr[i-1] }}
                </label>
              </div>
            </div>

            <a href="#" class="text-sm text-color-main mt-2">скрыть часть</a>
          </div>

          <div class="mt-10">
            <div class="flex justify-between items-center">
              <span class="text-sm text-color-main">Цвет</span>
              <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 10L8 6L4 10" stroke="#42474D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>

            <div class="flex flex-col mt-3">
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

            <a href="#" class="text-sm text-color-main mt-2">скрыть часть</a>
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

          <div class="tab flex space-x-3 mt-10">
            <div class="bg-tab-active py-3 px-5 rounded-lg text-gray-700 text-sm">
              По популярности
            </div>
            <div class="py-3 px-5 rounded text-gray-700 text-sm">
              Новинки
            </div>
            <div class="py-3 px-5 rounded text-gray-700 text-sm">
              Сначала дешёвые
            </div>
            <div class="py-3 px-5 rounded text-gray-700 text-sm">
              Сначала дорогие
            </div>
          </div>

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
                    <div class="flex items-center space-x-3 mt-3">
                      <button class="bg-gray-200 w-9 rounded h-9 text-4xl flex items-center justify-center">-</button>
                      <span>99</span>
                      <button class="bg-gray-200 w-9 rounded h-9 text-4xl flex items-center justify-center">+</button>
                    </div>
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
                    <div class="flex items-center space-x-3 mt-3">
                      <button class="bg-gray-200 w-9 rounded h-9 text-4xl flex items-center justify-center">-</button>
                      <span>99</span>
                      <button class="bg-gray-200 w-9 rounded h-9 text-4xl flex items-center justify-center">+</button>
                    </div>
                    <a href="#" class="block rounded py-3 px-4 text-white font-bold mt-2" style="background: #224386;">В корзину</a>
                  </div>
                </div>
              </div>
            </div>
          </div>

        </div>
      </div>

    </div>

    <FooterWhite />
  </div>
</template>

<script>
import FooterWhite from "@/components/FooterWhite";
import { ref } from 'vue'
import AppSlider from "@/components/AppSlider";
export default {
  components: {AppSlider, FooterWhite},
  setup() {
    const fitings = ["ФИТИНГИ", "Запорная арматура", "Коллекторы", "Труба армированная", "Труба не армированная", "Оборудование для монтажа", "Материалы для монтажа", "Другое"]
    const type_fitings = ["Муфта (21)", "Отводы и угольники (60)", "Тройники и крестовины (1)", "Запорная арматура (1)", "Другое (1)"]
    const size = ["1/2 (1)", "3/4 (1)", "1 (1)", "1,25 (1)", "1,5 (1)", "2 (1)", "3 (1)", "4 (1)"]
    const diametr = ["20 мм (60)", "25 мм (1)", "32 мм (1)", "40 мм (1)", "50 мм(1)", "63 мм (1)", "75 мм (1)", "90 мм (1)", "110 мм (1)", "125 мм(1)", "140 мм (1)", "160 мм(1)"]

    const sliderMin = ref(0);
    const sliderMax = ref(200);

    return {
      fitings,
      type_fitings,
      size,
      diametr,
      sliderMin,
      sliderMax
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

</style>