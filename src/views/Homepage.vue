<script>
    import axios from 'axios'
    import 'vue3-carousel/dist/carousel.css'
    import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'

    export default {
        name: 'App',
        data:() => ({
            image: "https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%2012%40300x-100.jpeg?alt=media&token=d1892713-898f-4036-b218-1ff56f050f5c",
            image1: "https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%208%40300x-100.jpeg?alt=media&token=29a2f604-2f6a-4fa6-b002-5e5a1321ef2a",
            image2: "https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%206%40300x-100.jpeg?alt=media&token=561c358d-0717-43c3-aa5f-d24114e1b347",
            image3: "https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%205%40300x-100.jpeg?alt=media&token=fe6957f4-e2a9-4a6b-8466-dd6026788313",
            settings: {
                itemsToShow: 1,
                snapAlign: 'center',
            },
            breakpoints: {
                600: {
                    itemsToShow: 1,
                    snapAlign: 'center',
                },

                1024: {
                    itemsToShow: 4,
                    snapAlign: 'start',
                },
            },
            dataSlide: ''
        }),
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
        <div class="hero bg-center bg-cover bg-fixed h-[700px] py-40 px-[100px] text-white max-sm:px-[50px]">
            <p class="text-5xl mb-10 w-1/2 max-sm:w-auto">WE CREATED & DEVELOP BRAND WITH PURPOSES</p>
            <p class="text-sm w-1/3 max-sm:w-auto">We create brand with purposes & clear vision specialized in create, develop & maintain reputable Brands</p>
            <p class=" mb-10">Lets grow with us</p>
            <div class="flex items-center">
                <input type="text" class=" bg-green-800 py-3 px-5 placeholder-white placeholder:text-sm" placeholder="Get to know us now...">
                <div class=" bg-green-900 py-3 px-5 cursor-pointer ">
                    <font-awesome-icon :icon="[ 'fas', 'arrow-down' ]" />
                </div>
            </div>
        </div>
    </header>
    <img src="https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/SBI%20Logo%20Full.png?alt=media&token=092f872c-d31d-4bd3-a96e-c4157b622009" alt="" class=" absolute right-5 top-[28rem] w-[25rem] z-0 max-sm:hidden">
    <section class="flex py-7">
        <div class="grid w-1/2 text-4xl px-20 py-10 gap-10">
            <p>WE BUILD BRAND</p>
            <p class=" ml-40">WITH LOVE</p>
            <p>AND PURPOSES</p>
            <p class="text-sm ml-20" >Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima, commodi quas? Aliquid ea possimus ad, quae doloremque consequatur deleniti magni officia doloribus aperiam sed illum ratione suscipit reprehenderit quod hic.</p>
        </div>
        <div class="w-1/2 flex justify-end">
            <img src="https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%203.png?alt=media&token=03b82cd1-183a-430f-98ce-474b6e369e64" class="w-1/2 z-[1] max-sm:hidden" alt=""/>
        </div>
    </section>
    <section class="flex max-sm:block">
        <div class=" flex w-2/3 text-sm max-sm:block max-sm:w-auto max-sm:text-center">
            <div class="w-1/4 p-10 bg-[#fffff5] max-sm:w-auto">
                <p class="text-[#34513f] text-4xl max-sm:mb-2">3424</p>
                <p>Lorem ipsum dolor, sit amet</p>
            </div>
            <div class="w-1/4 p-10 bg-[#edecda] max-sm:w-auto">
                <p class="text-[#34513f] text-4xl max-sm:mb-2">3424</p>
                <p>Lorem ipsum dolor, sit amet</p>
            </div>
            <div class="w-1/4 p-12 bg-[#fffff5] max-sm:w-auto">
                <p class="text-[#34513f] text-4xl max-sm:mb-2">3424</p>
                <p>Lorem ipsum dolor, sit amet</p>
            </div>
            <div class="w-1/4 p-10 bg-[#34513f] text-white max-sm:w-auto">
                
            </div>
        </div>
        <div class=" w-1/2 max-sm:w-auto max-sm:my-10">
            <img src="https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%204%40300x-100.jpeg?alt=media&token=7e2aec37-be93-4fab-af82-13b89aa91ed2" class="w-full h-[11rem] object-right-top object-cover" alt=""/>
        </div>
    </section>
    <section>
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
    <section class="flex max-sm:block">
        <div class="w-[25rem] h-[37rem] max-sm:hidden">
            <img src="https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%207%40300x-100.jpeg?alt=media&token=c73a5cb8-7933-43a3-82f1-494c520cae02" alt="" class=" w-[25rem] object-cover">
        </div>
        <div class="w-[70rem] max-sm:w-auto">
            <div class="flex gap-14 px-10 max-sm:block">
                <div class="w-1/3 py-16 text-4xl text-[#34513f] font-semibold max-sm:w-auto">
                    <p>Berkarir dan bergabung menjadi SBI Family</p>
                </div>
                <div class="w-1/2 py-16 max-sm:w-auto max-sm:py-10">
                    <p>Mari berinteraksi lebih dekat dengan kami, Brainstrom atau sekedar menjalin silahturahim. Tinggalkan kontak anda disni dan kami akan menghubungi anda</p>
                    <div class="flex text-white mt-10 gap-10 max-sm:grid max-sm:text-center max-sm:gap-5">
                        <a href="" class="bg-[#34513f] py-3 px-10 rounded-full">Daftar Sekarang</a>
                        <a href="" class="bg-[#34513f] py-3 px-10  rounded-full">Info Karir</a>
                    </div>
                </div>
            </div>
            <div class="flex max-sm:block">
                <div class="w-1/2 h-[19.4rem] bg-cover bg-center bg-no-repeat max-sm:w-auto" v-bind:style="{ backgroundImage: 'url(' + image1 + ')' }">
                </div>
                <div class="w-1/2 h-auto bg-center bg-cover bg-no-repeat"  v-bind:style="{ backgroundImage: 'url(' + image2 + ')' }">
                </div>
            </div>
        </div>
    </section>
    <section class="flex px-10 py-14">
        <div class="w-[25rem] h-[25rem] bg-cover bg-bottom max-sm:hidden" v-bind:style="{ backgroundImage: 'url(' + image3 + ')' }">
        </div>
        <div class="px-10 max-sm:p-0">
            <p class="text-[#34513f] text-3xl mb-5">Let's Discuss</p>
            <p>Mari berinteraksi lebih dekat dengan kami</p>
            <p>Brainstrom atau sekedar menjalin silaturahim </p>
            <p>Tinggalkan kontak anda disini dan kami akan menghubungi anda </p>
            <p class="text-[#34513f] text-3xl mt-16">Kontak sebagai</p>
            <div class="flex text-white mt-8 gap-10">
                <a href="" class="bg-[#34513f] py-3 px-10  rounded-full">Investor</a>
                <a href="" class="bg-[#34513f] py-3 px-10 rounded-full">Vendor</a>
            </div>
        </div>
    </section>
</template>

<style scoped>
    html{  
        background-color: #f8f8f8;
    }
    .hero{
        background-image: linear-gradient(to bottom, rgba(0,0,0,0.2) 0%,rgba(0,0,0,0.2) 100%),url('https://firebasestorage.googleapis.com/v0/b/kalih-165ab.appspot.com/o/Asset%2013%40300x-100.jpeg?alt=media&token=99c975a1-9cff-4e90-ac6e-be7e6400e65c');
        background-repeat: no-repeat;
    }

    #hero{
        margin-top: -7em;
    }


</style>