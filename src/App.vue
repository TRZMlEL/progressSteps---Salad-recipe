<template>
  <body class="w-screen h-screen bg-gray-900 p-5 flex flex-col items-center">
    <header class="w-5/6 h-1/5 bg-slate-100 mb-5 rounded-2xl relative">
      <div class="w-4/6 h-1/6 bg-gray-400 absolute -translate-x-1/2 left-1/2 -translate-y-1/2 top-1/2">
        <div :class="{'w-0': slide === 1, 'w-1/3': slide === 2, 'w-2/3': slide === 3, 'w-full': slide === 4}" class="h-full bg-emerald-600 transition-all duration-500 ease-out"></div>
      </div>
      <div class="w-4/6 h-full flex items-center justify-between absolute -translate-x-1/2 left-1/2 -translate-y-1/2 top-1/2">
        <div class="z-10 h-4/6 bg-gray-900 border-8 border-emerald-600 aspect-square rounded-full flex items-center justify-center text-slate-100 font-bold">1</div>
        <div :class="{'border-emerald-600': slide >= 2, 'border-gray-400': slide < 2}" class="z-10 h-4/6 bg-gray-900 border-8 aspect-square rounded-full flex items-center justify-center text-slate-100 font-bold transition-all duration-300 delay-300">2</div>
        <div :class="{'border-emerald-600': slide >= 3, 'border-gray-400': slide < 3}" class="z-10 h-4/6 bg-gray-900 border-8 aspect-square rounded-full flex items-center justify-center text-slate-100 font-bold transition-all duration-300 delay-300">3</div>
        <div :class="{'border-emerald-600': slide >= 4, 'border-gray-400': slide < 4}" class="z-10 h-4/6 bg-gray-900 border-8 aspect-square rounded-full flex items-center justify-center text-slate-100 font-bold transition-all duration-300 delay-300">4</div>
      </div>
    </header>
    <main class="w-5/6 h-4/6 bg-slate-100 mb-5 rounded-2xl text-gray-900">
      <div v-show="slide === 1" class="flex items-center justify-between w-full h-full p-10 gap-5 transition-all duration-300">
        <div class="h-full">
          <h1 class=" text-3xl font-bold mb-5">Przygotowanie składników</h1>
          <p class="text-xl font-semibold">Zbierz następujące składniki:</p>
          <ul class="text-xl list-disc ml-6">
            <li>sałata</li>
            <li>2 pomidory</li>
            <li>1 ogórek</li>
            <li>1 cebula</li>
            <li>100g sera feta</li>
            <li>oliwa z oliwek</li>
            <li>sól i pieprz do smaku</li>
          </ul>
        </div>
        <img src="https://th.bing.com/th/id/OIG.3xgWsc_5z.UwgWd_8HTK?pid=ImgGn" class="h-full aspect-square rounded-2xl" />
      </div>
      <div v-show="slide === 2" class="flex items-center justify-between w-full h-full p-10 gap-5 transition-all duration-300">
        <div class="h-full">
          <h1 class=" text-3xl font-bold mb-5">Przygotowanie warzyw</h1>
          <p class="text-xl font-semibold">Umyj pomidory, ogórka i cebulę. Następnie pokrój pomidory i ogórka na małe kawałki, a cebulę na cienkie plastry.</p>
        </div>
        <img src="https://th.bing.com/th/id/OIG.vZ_C4qqviwGEjP2A8zQX?pid=ImgGn" class="h-full aspect-square rounded-2xl" />
      </div>
      <div v-show="slide === 3" class="flex items-center justify-between w-full h-full p-10 gap-5 transition-all duration-300">
        <div class="h-full">
          <h1 class=" text-3xl font-bold mb-5">Dodanie sera</h1>
          <p class="text-xl font-semibold">Pokrój ser feta na małe kawałki i dodaj do sałatki.</p>
        </div>
        <img src="https://th.bing.com/th/id/OIG.0Du0k_4HZUg6ppDPpgEK?pid=ImgGn" class="h-full aspect-square rounded-2xl" />
      </div>
      <div v-show="slide === 4"  class="flex items-center justify-between w-full h-full p-10 gap-5 transition-all duration-300">
        <div class="h-full">
          <h1 class=" text-3xl font-bold mb-5">Doprawienie sałatki</h1>
          <p class="text-xl font-semibold">Dodaj do sałatki oliwę z oliwek, sól i pieprz do smaku. Delikatnie wymieszaj wszystko.</p>
          <p class="text-xl font-bold mt-5">Smacznego! 😊</p>
        </div>
        <img src="https://th.bing.com/th/id/OIG.By_Nnc8krYsNWsWMpr1r?pid=ImgGn&w=1024&h=1024&rs=1" class="h-full aspect-square rounded-2xl" />
      </div>
    </main>
    <footer  class="w-5/6 h-1/5 bg-slate-100 rounded-2xl flex items-center justify-center gap-10 text-slate-100 font-bold">
      <button @click="prev()" :class="{'bg-gray-400 ': slide === 1, 'bg-emerald-600': slide !== 1}" class=" w-32 h-1/2 rounded-xl">Prev</button>
      <button @click="next()" :class="{'bg-gray-400 ': slide === 4, 'bg-emerald-600': slide !== 4}" class="  w-32 h-1/2 rounded-xl">Next</button>
    </footer>
  </body>
</template>

<script setup>
import { ref } from 'vue';

let slide = ref(1)

const prev = () => {
  slide.value--
  if (slide.value == 0) {
    slide.value = 1
  }
  console.log(slide.value)
}

const next = () => {
  slide.value++
  if (slide.value == 5) {
    slide.value = 4
  }
  console.log(slide.value)
}
</script>