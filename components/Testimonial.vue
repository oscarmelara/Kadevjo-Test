<template>
<div>
    <div v-swiper:mySwiper="swiperTestimonial" class="px-6">
        <div class="swiper-wrapper" >
          <div 
            class="swiper-slide flex justify-center" 
            
          >
            <div class="w-full lg:w-4/5 xl:w-8/12 flex items-center px-6 lg:px-0 xl:px-0">
                <img class=" h-32 object-cover rounded-full -mr-10 z-10" src="~/assets/images/testimonio1.png" alt="">
                <div class="pl-16 py-12 pr-10 bg-white rounded-lg">
                <p class="text-sm text-gray-500 text-medium leading-snug">Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
                    Donec venenatis erat elit, non sollicitudin quam fringilla vitae.</p>
                <div class="flex mt-3 relative">
                    <div class="relative">
                    <h2 class="text-gray-700 font-bold text-base xl:text-lg">Carmen Aguilar</h2>
                    <p class="text-gray-700 font-semibold text-base">Gerente / Movistar</p>
                    </div>
                    <img class="absolute w-16 right-0 -mr-12" src="~/assets/images/comillas.svg" alt="">
                </div>
                </div>
            </div>
          </div>
          <div 
            class="swiper-slide" 
            
          >
            <div class="w-full lg:w-4/5 xl:w-8/12 flex items-center px-6 lg:px-0 xl:px-0">
                <img class=" h-32 object-cover rounded-full -mr-10 z-10" src="~/assets/images/testimonio2.png" alt="">
                <div class="pl-16 py-12 pr-10 bg-white rounded-lg">
                <p class="text-sm text-gray-500 text-medium leading-snug">Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
                    Donec venenatis erat elit, non sollicitudin quam fringilla vitae.</p>
                <div class="flex mt-3 relative">
                    <div class="relative">
                    <h2 class="text-gray-700 font-bold">Luis Gerardo</h2>
                    <p class="text-gray-700 font-semibold text-base">CEO / Donkey's</p>
                    </div>
                    <img class="absolute w-16 right-0 -mr-12" src="~/assets/images/comillas.svg" alt="">
                </div>
                </div>
            </div>
          </div>
         
        </div>
        <div class="swiper-pagination swiper-pagination-bullets"></div>
        <div class="swiper-button-prev" slot="button-prev"></div>
          <div class="swiper-button-next" slot="button-next"></div>
      </div>
</div>
    
</template>
<script>
import '@/assets/css/swiper.css';
export default {
    name: 'Testimonial',
    data: () => {
        return {
            swiperTestimonial: {
                loop: true,
                slidesPerView: '2',
                spaceBetween: 30,
                slidesPerGroup: 2,
                loopFillGroupWithBlank: true,
                navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev'
                },
                breakpoints: {
                    1024: {
                    slidesPerView: 2,
                    spaceBetween: 30
                    },
                    768: {
                    slidesPerView: 2,
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