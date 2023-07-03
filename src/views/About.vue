<script>
    import 'vue3-carousel/dist/carousel.css'
    import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
    import axios from 'axios'

    export default{
        data(){
            return{
                image1: "https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%208%40300x-100.jpeg?alt=media&token=29a2f604-2f6a-4fa6-b002-5e5a1321ef2a",
                settings: {
                    itemsToShow: 1,
                    snapAlign: 'start',
                },
                breakpoints: {
                    600: {
                        itemsToShow: 1,
                        snapAlign: 'center',
                    },

                    1024: {
                        itemsToShow: 4.5,
                        snapAlign: 'start',
                    },
                },
                settings1: {
                    itemsToShow: 1,
                    snapAlign: 'start',
                },
                breakpoints1: {
                    600: {
                        itemsToShow: 1,
                        snapAlign: 'center',
                    },

                    1024: {
                        itemsToShow: 2.5,
                        snapAlign: 'center',
                    },
                },
                settings2: {
                    itemsToShow: 1,
                    snapAlign: 'start',
                },
                breakpoints2: {
                    600: {
                        itemsToShow: 1,
                        snapAlign: 'center',
                    },

                    1024: {
                        itemsToShow: 3.5,
                        snapAlign: 'center',
                    },
                },
                dataSlide: '',
                dataSlide1: '',
                dataSlide2: ''
            }
        },
        components: {
            Carousel,
            Slide,
            Pagination,
            Navigation,
        },
        created(){
            this.getData()
        },
        methods:{
            getData(){
                axios.get('https://kalih-165ab-default-rtdb.firebaseio.com/slide_homepage.json')
                    .then(ress =>{
                        this.dataSlide = ress.data
                    })
                    .catch(err =>{
                        console.log(err)
                    })
            }
        }
    }
</script>

<template>
    <header id="hero">
        <div class="hero bg-center bg-cover bg-fixed h-[700px] py-48 px-[100px] text-white max-sm:px-[50px] max-sm:py-30">
            <p class="text-5xl mb-10 w-1/4 max-sm:text-4xl max-sm:w-auto">Kalih Coffe Tea and Space </p>
            <p class="text-sm w-1/2 mb-20">We create brand with purposes & clear vision specialized in create, develop & maintain reputable Brands</p>
            <div class="flex items-center">
                <input type="text" class=" bg-green-800 py-3 px-5 placeholder-white placeholder:text-sm" placeholder="Get to know us now...">
                <div class=" bg-green-900 py-3 px-5 cursor-pointer ">
                    <font-awesome-icon :icon="[ 'fas', 'arrow-down' ]" />
                </div>
            </div>
        </div>
    </header>
    <section class="px-24 py-20 flex gap-20 max-sm:block max-sm:p-10">
        <div class="w-1/2 bg-[#34513f] max-sm:hidden">
            <img src="" alt="">
        </div>
        <div class="w-1/2 max-sm:w-auto">
            <p class="text-4xl text-[#34513f] mb-10 font-semibold">Selayang Pandang</p>
            <p class="text-sm text-justify">Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati, cum officiis? Recusandae saepe natus quod a. Asperiores perspiciatis nemo quam est maxime ipsum fuga molestias quasi ratione soluta, quis fugit? Qui libero nihil et nesciunt animi modi vitae, ad temporibus consequatur placeat asperiores, quas, magni atque corporis accusantium voluptatibus voluptate voluptatum unde blanditiis exercitationem aliquam eos? Amet animi minima delectus ipsa vel, quos harum! Quis doloribus dolorum nam voluptatum illo, velit ut sapiente vero nulla pariatur repellendus perspiciatis reiciendis, omnis ullam fugiat non fuga? Sed, magni optio soluta, tempora nostrum ex laudantium illum exercitationem ratione asperiores, eos eligendi deserunt minima.</p>
        </div>
    </section>
    <section  class="px-24 py-20 gap-80 flex max-sm:p-10 max-sm:block">
        <div class=" w-1/2 max-sm:w-auto">
            <h6 class=" font-semibold mb-10">Overview</h6>
            <h6 class=" font-semibold text-5xl tracking-wider mb-16">Kalih, Coffe, Tea & Spaces</h6>
            <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Assumenda nihil eum incidunt dolor unde repellendus, eveniet hic voluptas. Ea, ipsam.</p>
            <div class="flex gap-10 mt-16">
                <div class="">
                    <h6 class=" font-semibold text-4xl mb-6">3452</h6>
                    <p>Lorem ipsum dolor sit amet</p>
                </div>
                <div class="">
                    <h6 class=" font-semibold text-4xl mb-6">3452</h6>
                    <p>Lorem ipsum dolor sit amet</p>
                </div>
                <div class="">
                    <h6 class=" font-semibold text-4xl mb-6">3452</h6>
                    <p>Lorem ipsum dolor sit amet</p>
                </div>
            </div>
        </div>
        <div class=" w-1/2 max-sm:w-auto">
            <div class=" bg-green-800 w-auto h-[32rem] py-14 px-20 max-sm:p-10 max-sm:h-[25rem] max-sm:mt-10">
                <div class=" bg-white ml-[-12rem] mr-[12rem] max-sm:m-0">
                    <img src="https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%206%40300x-100.jpeg?alt=media&token=561c358d-0717-43c3-aa5f-d24114e1b347" class=" object-cover object-bottom w-full h-[15rem]" alt="">
                    <div class="py-5 px-10 shadow-md">
                        <p class=" text-2xl mb-5 max-sm:text-xl">Where Location Kalih Space</p>
                        <a href="" class="flex text-[#34513f] border-[#34513f] border py-2 px-5 items-center gap-4 hover:bg-[#34513f] hover:text-white max-sm:text-xs">
                            <font-awesome-icon :icon="[ 'fas', 'map-marker' ]" />
                            <p>Open in Google Maps</p>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="px-24 h-[30rem]">
        
    </section>

    <section class="bg-[#34513f] py-5" >
        <div class="flex text-white py-14 px-20 justify-between max-sm:block">
            <div class=" w-[9%] text-4xl max-sm:w-auto">
                <p class=" leading-relaxed">Our Looks & View</p>
            </div>
            <div class=" w-1/2 max-sm:w-auto">
                <p class=" mb-14">Lorem ipsum dolor sit amet consectetur adipisicing elit. Et dolorum mollitia possimus velit. Soluta doloremque exercitationem temporibus quam reprehenderit deleniti quisquam consectetur atque error voluptatum qui, aliquam, corrupti facere quaerat!</p>
                <a href="" class=" py-2 px-5 bg-white text-[#34513f] rounded-full">Download Our Menu</a>
            </div>
        </div>
        <div class="mb-10">
            <carousel :settings="settings1" :breakpoints="breakpoints1" wrap-around="@loop" autoplay="3000" :transition="1000">
                <slide v-for="slide in 10" :key="slide">
                    <div class="mr-5">
                        <img src="https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%206%40300x-100.jpeg?alt=media&token=561c358d-0717-43c3-aa5f-d24114e1b347" class="object-cover object-center  h-[20rem] w-[50rem]" alt="">
                    </div>
                </slide>
            </carousel>
        </div>
        <div class="mb-10">
            <carousel :settings="settings2" :breakpoints="breakpoints2" wrap-around="@loop" autoplay="3000" :transition="1000">
                <slide v-for="slide in 10" :key="slide" >
                    <div class="mr-5">
                        <img src="https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%206%40300x-100.jpeg?alt=media&token=561c358d-0717-43c3-aa5f-d24114e1b347"  class="object-cover object-center  h-[20rem] w-[30rem]" alt="">
                    </div>
                </slide>
            </carousel>
        </div>
    </section>
    <section class="mt-96 mb-10" >
        <carousel :settings="settings" :breakpoints="breakpoints" wrap-around="@loop" autoplay="3000" :transition="1000">
            <slide v-for="slide in dataSlide" :key="slide.id">
                <div class=" bg-cover bg-center w-full h-[30rem]" v-bind:style="{ backgroundImage: 'url(' + slide.image + ')' }">
                    <div class="text-white text-left bg-gradient-to-r from-[rgba(0,0,0,0.2)] to-[rgba(0,0,0,0.2)] w-auto h-full py-40 px-10">
                        <p class="text-3xl mb-10 w-44">{{slide.title}}</p>
                        <a href="" class=" rounded-full border-white border-2 p-2 text-sm">Learn More</a>
                    </div>
                </div>
            </slide>
        </carousel>
    </section>
</template>

<style scoped>
    .con{  
        background-color: white;
    }

    .hero{
        background-image: linear-gradient(to bottom, rgba(0,0,0,0.2) 0%,rgba(0,0,0,0.2) 100%),url('https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%204%40300x-100.jpeg?alt=media&token=7e2aec37-be93-4fab-af82-13b89aa91ed2');
        background-repeat: no-repeat;
    }

    #hero{
        margin-top: -7em;
    }
</style>