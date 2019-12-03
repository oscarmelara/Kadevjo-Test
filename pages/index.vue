<template>
<div>
  <section class="w-full header-section bg-cover bg-center block relative">
    <div class="absolute w-full h-full z-10 justify-end items-center right-0 hidden md:flex lg:flex xl:flex">
      <img class=" w-5/12 mt-12" src="~/assets/images/photo.png" alt="">
    </div> 
    <div class="container h-full mx-auto flex items-center">
      <div class="static lg:absolute xl:absolute intro-header w-full lg:w-2/5 xl:w-2/5 px-3 lg:px-0 xl:px-0">
        <h1 class="text-gray-500 font-bold text-4xl lg:text-5xl xl:text-6xl leading-none">Encuentra el empleo ideal</h1>
        <form class="mt-8" action="">
          <div class="flex items-center">
            <input class=" rounded-lg w-full lg:w-1/2 xl:w-1/2 h-10" type="text">
            <button class="ml-4 button-search bg-center bg-cover rounded-full h-10 w-10" ></button>
          </div>
        </form>
        <div class="w-full flex justify-end mt-6 block md:hidden">
          <img class=" w-1/2 absolute right-0" src="~/assets/images/photo.png" alt="">
        </div>
      </div>
      
    </div>
    
  </section>

  <section class="w-full py-6">
    <div class="container mx-auto px-10">
      <h1 class="text-gray-500 font-bold text-4xl text-center mb-10">Ofertas nuevas</h1>
      <slider-offer />
      
    </div>
  </section>

  <section class="w-full py-10">
    <div class="container mx-auto flex flex-wrap">
      <div class="w-full lg:w-3/5 xl:w-3/5 flex justify-center z-10 relative">
          <img class="lg:absolute xl:absolute w-10/12" src="~/assets/images/cv.svg" alt="">
      </div>
      <div class="w-full lg:w-2/5 xl:w-2/5 flex flex-col items-start justify-center px-6 z-10">
        <h1 class="text-gray-500 font-bold text-4xl lg:text-5xl xl:text-6xl leading-none">
          Crea tu curriculum vitae
        </h1>
        <h2 class="text-gray-700 font-bold text-3xl">Descarga tu plantilla</h2>
        <button class="rounded-lg bg-blue-800 hover:border-blue-800 hover:text-blue-800 hover:bg-transparent border w-full lg:w-1/2 xl:w-1/2 py-2 px-2 text-white font-bold mt-4">Primer empleo</button>
        <button class="rounded-lg bg-blue-800 hover:border-blue-800 hover:text-blue-800 hover:bg-transparent border w-full lg:w-1/2 xl:w-1/2 py-2 px-2 text-white font-bold mt-3">Experiencia Laboral</button>
      </div>
    </div>
  </section>

  <section class="w-full our-section relative h-full lg:h-screen xl:h-screen flex flex-col items-center justify-center">
    <div class="hidden lg:block xl:block lg:absolute xl:absolute w-full">
      <img src="~/assets/images/blue-background.svg" alt="">
    </div>
    <div class="container mx-auto flex justify-center items-center flex-col mt-12 lg:mt-56 xl:mt-56">
      <h2 class="z-10 text-white font-bold text-4xl text-center mb-6 mt-10">Quienes Somos</h2>
      <div class="flex justify-around w-full flex-wrap px-6">
        <div class="w-1/2 lg:w-1/4 xl:w-1/4 z-10 flex flex-col justify-center items-center">
          <h1 class="text-white font-bold text-3xl lg:text-4xl xl:text-6xl">1,800</h1>
          <p class=" text-yellow-700 text-center xl:text-lg">Empleos otorgados</p>
        </div>
        <div class="w-1/2 lg:w-1/4 xl:w-1/4 z-10 flex flex-col justify-center items-center">
          <h1 class="text-white font-bold text-3xl lg:text-4xl xl:text-6xl">900</h1>
          <p class=" text-yellow-700 text-center xl:text-lg">Empresas registradas</p>
        </div>
        <div class="w-1/2 lg:w-1/4 xl:w-1/4 z-10 flex flex-col justify-center items-center">
          <h1 class="text-white font-bold text-3xl lg:text-4xl xl:text-6xl">820</h1>
          <p class=" text-yellow-700 text-center xl:text-lg">Profesionales registrados</p>
        </div>
        <div class="w-1/2 lg:w-1/4 xl:w-1/4 z-10 flex flex-col justify-center items-center">
          <h1 class="text-white font-bold text-3xl lg:text-4xl xl:text-6xl">1,250</h1>
          <p class=" text-yellow-700 text-center xl:text-lg">Oportunidades de empleo</p>
        </div>
      </div>
      <div class="flex flex-wrap flex-col-reverse lg:flex-row xl:flex-row z-10 mt-6 lg:px-20 xl:px-20">
        <div class="w-full lg:w-1/2 xl:w-3/5 flex justify-center rounded-lg px-6 lg:px-12 mt-6 lg:mt-0 xl:mt-0">
          <GmapMap
            v-bind:center="centers"
            v-bind:zoom="7"
            map-type-id="terrain"
            style="width: 100%; height: 300px"
            class="rounded-lg"
          >
            <GmapMarker
              :key="index"
              v-for="(m, index) in markers"
              v-bind:position="m.position"
              v-bind:clickable="true"
              v-bind:draggable="true"
              @click="center=m.position"
            />
          </GmapMap>
        </div>
        <div class="w-full lg:w-2/5 xl:w-2/5 pr-12 flex flex-col justify-center px-6 lg:px-0 xl:px-0">
          <h1 class="text-yellow-700 font-bold text-3xl">Gestion de empleos</h1>
          <p class="text-white w-full lg:w-2/3 xl:w-4/5">Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
            Donec venenatis erat elit, non sollicitudin quam fringilla vitae.</p>
        </div>
      </div>
    </div>
  </section>

  <section class="w-full py-24 contact-company bg-bottom bg-contain bg-no-repeat relative z-10">
    <div class="container mx-auto flex flex-wrap px-6 lg:px-0 xl:px-0 lg:mt-10 xl:mt-16 mt-0 lg:px-4">
      <div class="w-full lg:w-1/2 xl:w-1/2 flex justify-end">
        <div class="w-full lg:w-1/2 xl:w-1/2 flex flex-col justify-center">
            <h1 class="text-gray-500 font-bold text-4xl lg:text-5xl xl:text-6xl leading-none">
              Soy una empresa</h1>
            <p class="text-gray-500 mt-2 lg:mt-6 xl:mt-6">quiero publicar las ofertas de empleo vigentes</p>

        </div>
      </div>
      <div class="w-full lg:w-1/2 xl:w-1/2 flex justify-end mt-3 lg:mt-0 xl:mt-0">
        <div class="w-full lg:w-1/2 xl:w-1/2">
          <form class="mt-3" action="">
            <input class="rounded-lg w-1/2 h-10 border-gray-500 border w-full" type="text">
             <input class="rounded-lg w-1/2 h-10 border-gray-500 border mt-3 w-full" type="text">
              <textarea class="rounded-lg w-1/2  border-gray-500 border mt-3 w-full" rows="3" ></textarea>
              <button class="rounded-lg bg-blue-800 hover:border-blue-800 hover:text-blue-800 hover:bg-transparent border w-full lg:w-1/2 xl:w-1/2 py-2 px-2 text-white font-bold mt-4">Enviar</button>
          </form>
        </div>
      </div>
    </div>
  </section>

  <section class="testimonial-section w-full py-12 h-full lg:h-screen xl:h-screen flex items-center lg:-mt-24 xl:-mt-24">
    <div class="container mx-auto">
      <testimonial/>
    </div>

  </section>
</div>
</template>

<script>
import Testimonial from '~/components/Testimonial.vue'
import SliderOffer from '~/components/SliderOffer.vue'

export default {
  components: {
    Testimonial,
    SliderOffer
  },
  data: () => {
      return {
        centers: {
          lat: 13.69, lng:  -89.19
        },
        markers:[
          {
            position: { lat: 13.69, lng: -89.19 }
          },
        ],
        
      }
    },
    
}
</script>
<style lang="scss" scope>
/* Main Header */
.header-section {
  background-image: url('~assets/images/header.svg');
  height: 900px;

  @media (min-width: 1500px){
    height: 1200px;
  }

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

/* Border Map Google */
.vue-map {
  border-radius: 3%;
}

/* Section Ours */
.our-section {
  background-color: white;
  @media (max-width: 768px){
          background-image: url('~assets/images/blue-background.svg');
          background-size: cover;
        }
}

/* Section Contact */
.contact-company{
  background-image: url('~assets/images/edificios.svg')
}

/* Section Testimonial Slider */
.testimonial-section{
  background-image: url('~assets/images/circle.svg');
}

/* Swiper Buttons */
.swiper-button-prev{
  background-image: url('~assets/images/arrow-back.svg');
}

.swiper-button-next {
  background-image: url('~assets/images/arrow-front.svg')
}
</style>
