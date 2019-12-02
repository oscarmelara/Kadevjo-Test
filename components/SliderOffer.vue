<template>
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
                <div class="flex items-center">
                  <h1 class="text-gray-700 font-bold text-2xl leading-none">{{ place.name }}</h1>
                  <img src="@/assets/images/heart.png" alt="">
                </div>
                <div class="mt-2">
                  <p class="font-semibold text-gray-500">{{ place.company }}</p>
                  <p class="text-gray-400 text-sm flex items-center mt-3"><img class="mr-2" src="@/assets/images/flag.png" alt="">{{ place.city }}</p>
                </div>
              </div>
            </div>
          </div>
         
        </div>
      <div class="swiper-pagination swiper-pagination-bullets"></div>
      <div class="swiper-button-prev" slot="button-prev"></div>
        <div class="swiper-button-next" slot="button-next"></div>
    </div>
</template>
<script>
import 'swiper/dist/css/swiper.css'

export default {
    name: 'SliderOffer',
    data: () => {
        return {
            places: [
                {image: "https://raw.githubusercontent.com/oscarmelara/Kadevjo-Test/master/assets/images/plaza1.png", name: "Pasantia en diseño grafico", company: "Agencia Digital", city: "San Salvador, El Salvador"},
                {image: "https://raw.githubusercontent.com/oscarmelara/Kadevjo-Test/master/assets/images/plaza2.png", name: "Pasantia en diseño grafico", company: "Agencia Digital", city: "San Salvador, El Salvador"},
                {image: "https://raw.githubusercontent.com/oscarmelara/Kadevjo-Test/master/assets/images/plaza3.png", name: "Pasantia en Fotografia", company: "Agencia Digital", city: "San Salvador, El Salvador"},
                {image: "https://raw.githubusercontent.com/oscarmelara/Kadevjo-Test/master/assets/images/plaza4.png", name: "Pasantia en Desarrollador Web", company: "Agencia Digital", city: "San Salvador, El Salvador"}
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
          },
          breakpoints: {
            1024: {
              slidesPerView: 4,
              spaceBetween: 30
            },
            768: {
              slidesPerView: 3,
              spaceBetween: 30
            },
            640: {
              slidesPerView: 1,
              spaceBetween: 40
            },
            320: {
              slidesPerView: 1,
              spaceBetween: 10
            }
          }
          
          
        }
        }
    }    
}
</script>