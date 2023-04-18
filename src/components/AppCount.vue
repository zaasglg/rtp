<template>
  <div class="flex items-center space-x-3 mt-3">
    <button @click="minus" class="bg-gray-200 w-9 rounded h-9 text-4xl flex items-center justify-center">-</button>
    <span>{{ count }}</span>
    <button @click="plus" class="bg-gray-200 w-9 rounded h-9 text-4xl flex items-center justify-center">+</button>
  </div>
</template>

<script>
import {ref} from 'vue';

export default {
  setup () {
    const count = ref(1)

    const minus = () => {
      if (count.value > 1) {
        count.value--
      }
    }

    const plus = () => {
      count.value++
    }

    return {
      count,
      plus,
      minus
    }
  }
}
</script>

<style scoped>

</style>