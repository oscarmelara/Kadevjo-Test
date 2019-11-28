<template>
<div class="fixed w-full">
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
}
</script>