<template>
<div>
<footer class="w-full bg-gray-900">
    <div class="container mx-auto flex flex-wrap">
        <div class="flex py-6 lg:py-16 xl:py-16 w-full lg:w-1/3 xl:w-1/3 justify-center items-center ">
            <div >
                <img src="~/assets/images/places.svg" alt="">
            </div>
            <div class=" w-9/12 px-6">
                <P class="uppercase text-white text-sm">Oficinas centrales</P>
                <p class="text-white text-sm">Direccion: Alameda Juan Pablo II,
                    Avenida Cuscatancingo, #320
                </p>
            </div>
        </div>
        <div class="flex py-6 lg:py-16 xl:py-16 w-full lg:w-1/3 xl:w-1/3 justify-center items-center">
            <div >
                <img src="~/assets/images/phone.svg" alt="">
            </div>
            <div class=" w-9/12 px-6">
                <P class="uppercase text-white text-sm">Punto de atencion empresarial</P>
                <p class="text-white text-sm">25116000 ext 1343
                </p>
                <P class="uppercase text-white text-sm">Punto de atencion ciudadano</P>
                <p class="text-white text-sm">2511-6040
                </p>
            </div>
        </div>
        <div class="flex py-6 lg:py-16 xl:py-16 w-full lg:w-1/3 xl:w-1/3 justify-center items-center">
            <div >
                <img src="~/assets/images/time.svg" alt="">
            </div>
            <div class=" w-9/12 px-6">
               
                <p class="text-white text-sm">Horario de Atencion: De Lunes a Viernes de 8:00 a.m. a 4:00 p.m.
                </p>
            </div>
        </div>
        <div class="w-full py-6">
            <p class="text-gray-600 text-sm text-center">©2019 Alcaldía de la Ciudad de San Salvador.Todos los Derechos Reservados Alameda Juan Pablo II y Avenida Cuscatancingo No 320 San Salvador, El Salvador</p>
        </div>
    </div>
</footer>
</div>  
</template>
<script>
export default {
    name: 'MainFooter'
}
</script>