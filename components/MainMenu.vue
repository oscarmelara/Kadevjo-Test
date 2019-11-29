<template>
<div class="fixed w-full z-50 hidden lg:block xl:block" :class="{navbar: scrollPosition < 100, navbarColor: scrollPosition > 100}">
    <div class="container mx-auto py-6 flex">
        <div class="w-1/3">
            <img class="w-1/2" src="@/assets/images/logo-menu.png" alt="logo">
        </div>
        <div class="w-8/12">
            <ul class="flex justify-around h-full">
                <li class="flex items-center"><router-link class="text-gray-700" to="" >opcion</router-link></li>
                <li class="flex items-center"><router-link class="text-gray-700" to="" >opcion</router-link></li>
                <li class="flex items-center"><router-link class="text-gray-700" to="" >opcion</router-link></li>
                <li class="flex items-center"><router-link class="text-gray-700" to="" >opcion</router-link></li>
                <li class="flex items-center"><router-link class="text-gray-700" to="" >Iniciar sesion</router-link></li>
            </ul>
        </div>
    </div>
</div>
    
</template>
<script>
import logo from '@/assets/images/logo-menu.png'
export default {
     name: 'MainMenu',
     data: () => {
         return {
            scrollPosition: null
         }
         
     },
     methods: {
         updateScroll() {
            this.scrollPosition = window.scrollY
        }
     },
     mounted() {
        window.addEventListener('scroll', this.updateScroll);
    }
}
</script>
<style lang="scss" scoped>
.navbar{
    background-color: transparent;
    transition-duration: 0.5s;
}
.navbarColor{
    background-color: white;
    transition-duration: 0.5s;
}
</style>