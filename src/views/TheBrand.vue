<script>
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import axios from 'axios';



export default {
   data(){
    return{
        image1: "https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%208%40300x-100.jpeg?alt=media&token=29a2f604-2f6a-4fa6-b002-5e5a1321ef2a",
        settings: {
                itemsToShow: 1,
                snapAlign: 'start',
            },
        breakpoints: {
                700: {
                    itemsToShow: 1,
                    snapAlign: 'center',
                },

                1024: {
                    itemsToShow: 4.5,
                    snapAlign: 'start',
                },
            },
            dataSlide: ''
        }
   },
   created(){
        this.getData()
    },
   components: {
        Carousel,
        Slide,
        Pagination,
        Navigation,
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
    
};
</script>

<template>
    <header id="hero">
        <div class="hero bg-center bg-cover bg-fixed h-[700px] py-48 px-[100px] text-white">
            <p class="text-5xl mb-10 w-1/4">Kalih Coffe Tea and Space </p>
            <p class="text-sm w-1/2 mb-20">We create brand with purposes & clear vision specialized in create, develop & maintain reputable Brands</p>
            <div class="flex items-center">
                <input type="text" class=" bg-green-800 py-3 px-5 placeholder-white placeholder:text-sm" placeholder="Get to know us now...">
                <div class=" bg-green-900 py-3 px-5 cursor-pointer ">
                    <font-awesome-icon :icon="[ 'fas', 'arrow-down' ]" />
                </div>
            </div>
        </div>
    </header>
    <section class="flex p-20">
        <div class=" w-1/2 h-[40rem] py-20 px-10">
            <p class="text-4xl text-[#34513f] mb-10">Selayang Pandang</p>
            <p class="text-sm text-justify">Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati, cum officiis? Recusandae saepe natus quod a. Asperiores perspiciatis nemo quam est maxime ipsum fuga molestias quasi ratione soluta, quis fugit? Qui libero nihil et nesciunt animi modi vitae, ad temporibus consequatur placeat asperiores, quas, magni atque corporis accusantium voluptatibus voluptate voluptatum unde blanditiis exercitationem aliquam eos? Amet animi minima delectus ipsa vel, quos harum! Quis doloribus dolorum nam voluptatum illo, velit ut sapiente vero nulla pariatur repellendus perspiciatis reiciendis, omnis ullam fugiat non fuga? Sed, magni optio soluta, tempora nostrum ex laudantium illum exercitationem ratione asperiores, eos eligendi deserunt minima.</p>
            <div class=" con w-[45rem] h-[10rem] flex z-10 relative p-10  text-center border-l-4 border-[#34513f] mt-10 shadow-md">
                <div class=" w-1/3 text-sm">
                    <p class="text-4xl mb-2 font-semibold text-[#34513f]">3452</p>
                    <p>Lorem, ipsum dolor sit amet consectetur </p>
                </div>
                <div class=" w-1/3 text-sm ">
                    <p class="text-4xl mb-2 font-semibold text-[#34513f]">3452</p>
                    <p>Lorem, ipsum dolor sit amet consectetur </p>
                </div>
                <div class=" w-1/3 text-sm">
                    <p class="text-4xl mb-2 font-semibold text-[#34513f]">3452</p>
                    <p>Lorem, ipsum dolor sit amet consectetur </p>
                </div>
            </div>
        </div>
        <div class="w-1/2 bg-cover bg-center z-0" v-bind:style="{ backgroundImage: 'url(' + image1 + ')' }">
    </div>    
    </section>
    <section class=" px-32">
        <p class="text-4xl mb-14 font-semibold text-[#34513f]">Meet The Founders</p>
        <carousel :settings="settings" :breakpoints="breakpoints" wrap-around="@loop" autoplay="3000" :transition="1000">
            <slide v-for="slide in 10" :key="slide">
                <div class="text-left w-full mr-5">
                    <div class=" bg-[#34513f] h-[20rem]"></div>
                    <p class="text-base mt-7">Founder</p>
                    <p class="text-xl font-semibold mt-1">Mr Fulan bin Fulan</p>
                    <p class=" text-[#c0c0c0] mt-2">Chief Executif Officer</p>
                </div>
            </slide>
        </carousel>
    </section>
    <section class="py-10">

    </section>
    <section class="my-20">
        <carousel :settings="settings" :breakpoints="breakpoints" wrap-around="@loop" autoplay="3000" :transition="1000">
            <slide v-for="slide in dataSlide" :key="slide.id">
                <div class=" bg-cover bg-center w-full h-[30rem]" v-bind:style="{ backgroundImage: 'url(' + slide.image + ')' }">
                    <div class="text-white text-left bg-gradient-to-r from-[rgba(0,0,0,0.2)] to-[rgba(0,0,0,0.2)] w-auto h-full py-40 px-10">
                        <p class="text-3xl mb-10 w-[12.5rem]">{{slide.title}}</p>
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