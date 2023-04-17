<template>
  <div class="slider">
    <div class="carousel slide" data-bs-ride="carousel">
      <!-- Слайды -->
      <div class="carousel-inner">
        <div v-for="(slide, index) in slides" :key="index" class="carousel-item" :class="{ active: index === currentSlide }">
          <!-- Разметка слайда -->
          <img :src="slide.imgSrc" :alt="slide.imgAlt" class="d-block w-100">
          <div class="carousel-caption">
            <h3>{{ slide.title }}</h3>
            <p>{{ slide.description }}</p>
          </div>
        </div>
      </div>
      <!-- Кнопки переключения слайдов -->
      <a class="carousel-control-prev" href="#" role="button" @click="prevSlide">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Предыдущий</span>
      </a>
      <a class="carousel-control-next" href="#" role="button" @click="nextSlide">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Следующий</span>
      </a>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const currentSlide = ref(0); // Индекс текущего слайда
    const slides = [
      { imgSrc: 'img/slide1.jpg', imgAlt: 'Slide 1', title: 'Заголовок слайда 1', description: 'Описание слайда 1' },
      { imgSrc: 'img/slide2.jpg', imgAlt: 'Slide 2', title: 'Заголовок слайда 2', description: 'Описание слайда 2' },
      { imgSrc: 'img/slide3.jpg', imgAlt: 'Slide 3', title: 'Заголовок слайда 3', description: 'Описание слайда 3' }
    ]; // Массив слайдов

    // Метод для переключения на предыдущий слайд
    const prevSlide = () => {
      currentSlide.value = (currentSlide.value - 1 + slides.length) % slides.length;
    };

    // Метод для переключения на следующий слайд
    const nextSlide = () => {
      currentSlide.value = (currentSlide.value + 1) % slides.length;
    };

    return {
      currentSlide,
      slides,
      prevSlide,
      nextSlide
    };
  }
}
</script>

<style scoped>
  .slider .carousel {
    /* Ваши стили для слайдера */
  }

  .slider .carousel-item {
    /* Ваши стили для слайда */
  }

  .slider .carousel-caption {
    /* Ваши стили для заголовка и описания слайда */
  }

  .slider .carousel-control-prev,
  .slider .carousel-control-next {
    /* Ваши стили для кнопок переключения слайдов */
  }
</style>
