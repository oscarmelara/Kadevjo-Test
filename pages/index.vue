<template>
<div>
  <section class="w-full header-section bg-cover bg-center block relative">
    <div class="absolute w-full h-full z-10 flex justify-end items-center right-0 ">
      <img class=" w-5/12 mt-12" src="~/assets/images/photo.png" alt="">
    </div> 
    <div class="container h-full mx-auto flex items-center ">
      <div class="absolute intro-header w-2/5">
        <h1 class="text-gray-500 font-extrabold lg:text-5xl xl:text-6xl leading-none">Encuentra el empleo ideal</h1>
        <form class="mt-8" action="">
          <div class="flex items-center">
            <input class=" rounded-lg w-1/2 h-10" type="text">
            <button class="ml-4 button-search bg-center bg-cover rounded-full h-10 w-10" ></button>
          </div>
        </form>
      </div>
    </div>
    
  </section>
  <section class="w-full py-6">
    <div class="container mx-auto px-10">
      <h1 class="text-gray-600 font-bold text-3xl text-center mb-6">Ofertas nuevas</h1>
      <div v-swiper:mySwiper="swiperOption" class="px-6">
        <div class="swiper-wrapper" >
          <div 
            class="swiper-slide" 
            v-for="(place, index) in places" 
            :key="index"
          >
            <div class="bg-gray-100 rounded-lg">
              <div class="relative">
                <span class="px-4 flex items-center text-white font-semibold h-10 bg-yellow-600 absolute rounded-full mt-4 ml-4">Nuevo</span>
                <img class="h-48 object-cover w-full rounded-t-lg" :src="place.image" alt="">
              </div>
              <div class="p-4">
                <div>
                  <h1 class="text-gray-700 font-bold text-2xl leading-none">{{ place.name }}</h1> 
                </div>
                <div class="mt-2">
                  <p class="font-semibold text-gray-500">{{ place.company }}</p>
                  <p class="text-gray-400 text-sm">{{ place.city }}</p>
                </div>
              </div>
            </div>
          </div>
         
        </div>
    <div class="swiper-pagination swiper-pagination-bullets"></div>
    <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-button-next" slot="button-next"></div>
  </div>
      <!-- <div class="flex">
        <div class=" bg-gray-100 rounded-lg">
          <div class="relative">
            <span class="px-4 flex items-center text-white font-semibold h-10 bg-yellow-600 absolute rounded-full mt-4 ml-4">Nuevo</span>
            <img class="h-48 object-cover w-full rounded-t-lg" src="~/assets/images/plaza1.png" alt="">
          </div>
          <div class="p-4">
            <div>
              <h1 class="text-gray-700 font-bold text-2xl leading-none">Pasantia en diseño grafico</h1> 
            </div>
            <div class="mt-2">
              <p class="font-semibold text-gray-500">Nombre de la empresa</p>
              <p class="text-gray-400 text-sm">San Salvador, El Salvador</p>
            </div>
          </div>
        </div>
      </div> -->
    </div>
  </section>

  <section class="w-full py-10">
    <div class="container mx-auto flex">
      <div class="w-3/5 flex justify-center z-10 relative">
          <img class="absolute w-10/12" src="~/assets/images/cv.svg" alt="">
      </div>
      <div class=" w-2/5 flex flex-col items-start justify-center px-6">
        <h1 class="text-gray-500 font-extrabold lg:text-5xl xl:text-6xl leading-none">
          Crea tu curriculum vitae
        </h1>
        <h2 class="text-gray-700 font-bold text-3xl">Descarga tu plantilla</h2>
        <button class="rounded-lg bg-blue-800 w-full lg:w-1/2 xl:w-1/2 py-2 px-2 text-white font-bold mt-4">Primer empleo</button>
        <button class="rounded-lg bg-blue-800 w-full lg:w-1/2 xl:w-1/2 py-2 px-2 text-white font-bold mt-3">Experiencia Laboral</button>
      </div>
    </div>
  </section>
  <section class="w-full our-section relative h-screen flex flex-col items-center justify-center">
    <div class="absolute -mt-24">
      <img src="~/assets/images/blue-background.svg" alt="">
    </div>
    <div class="container mx-auto flex justify-center items-center flex-col">
      
      <h2 class="z-10 text-white font-bold text-3xl text-center mb-6 mt-10">Quienes Somos</h2>
      <div class="flex justify-around w-full">
        <div class="z-10 flex flex-col justify-center items-center">
          <h1 class="text-white font-extrabold text-5xl">1,800</h1>
          <p class=" text-yellow-700">Empleos otorgados</p>
        </div>
        <div class="z-10 flex flex-col justify-center items-center">
          <h1 class="text-white font-extrabold text-5xl">900</h1>
          <p class=" text-yellow-700">Empresas registradas</p>
        </div>
        <div class="z-10 flex flex-col justify-center items-center">
          <h1 class="text-white font-extrabold text-5xl">820</h1>
          <p class=" text-yellow-700">Profesionales registrados</p>
        </div>
        <div class="z-10 flex flex-col justify-center items-center">
          <h1 class="text-white font-extrabold text-5xl">1,250</h1>
          <p class=" text-yellow-700">Oportunidades de empleo</p>
        </div>
      </div>
      <div class="flex z-10 mt-6 px-20">
        <div class=" w-3/5 flex justify-center">
          <img src="~/assets/images/plaza1.png" alt="">
        </div>
        <div class=" w-2/5">
          <h1 class="text-yellow-700 font-bold text-xl">Gestion de empleos</h1>
          <p class="text-white">orem ipsum dolor sit amet, consectetur adipiscing elit. 
            Donec venenatis erat elit, non sollicitudin quam fringilla vitae.</p>
        </div>
      </div>
    </div>
  </section>
  
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import 'swiper/dist/css/swiper.css'



export default {
  components: {
    Logo,
    
  },
  data: () => {
      return {
        places: [
          {image: "~/assets/images/plaza1.png", name: "Pasantia en diseño grafico", company: "Agencia Digital", city: "San Salvador, El Salvador"},
          {image: "~/assets/images/plaza2.png", name: "Pasantia en diseño grafico", company: "Agencia Digital", city: "San Salvador, El Salvador"},
          {image: "~/assets/images/plaza3.png", name: "Pasantia en Fotografia", company: "Agencia Digital", city: "San Salvador, El Salvador"},
          {image: "~/assets/images/plaza4.png", name: "Pasantia en Desarrollador Web", company: "Agencia Digital", city: "San Salvador, El Salvador"}
         
        ],
        swiperOption: {
          loop: true,
          slidesPerView: '4',
          spaceBetween: 30,
          slidesPerGroup: 2,
          loopFillGroupWithBlank: true,
          
          pagination: {
            el: '.swiper-pagination',
            clickable: true
          },
          navigation: {
            nextEl: '.swiper-button-next',
            prevEl: '.swiper-button-prev'
          }
          
        }
      }
    },
    
}
</script>

<style lang="scss" scope>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.header-section {
  background-image: url('~assets/images/header.svg');
  height: 900px;


  .intro-header {
    left: 25%;
    top: 25%;
    @media (max-width: 1200px){
          left: 22%;
          top: 25%;
        }
      .button-search{
        background-image: url('~assets/images/search.svg');
        
      }
  }
}

/* Swiper Slider */

</style>
