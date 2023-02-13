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
    <section class="px-24 py-20 flex gap-20">
        <div class="w-1/2 bg-[#34513f]">
            <img src="" alt="">
        </div>
        <div class="w-1/2">
            <p class="text-4xl text-[#34513f] mb-10 font-semibold">Selayang Pandang</p>
            <p class="text-sm text-justify">Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati, cum officiis? Recusandae saepe natus quod a. Asperiores perspiciatis nemo quam est maxime ipsum fuga molestias quasi ratione soluta, quis fugit? Qui libero nihil et nesciunt animi modi vitae, ad temporibus consequatur placeat asperiores, quas, magni atque corporis accusantium voluptatibus voluptate voluptatum unde blanditiis exercitationem aliquam eos? Amet animi minima delectus ipsa vel, quos harum! Quis doloribus dolorum nam voluptatum illo, velit ut sapiente vero nulla pariatur repellendus perspiciatis reiciendis, omnis ullam fugiat non fuga? Sed, magni optio soluta, tempora nostrum ex laudantium illum exercitationem ratione asperiores, eos eligendi deserunt minima.</p>
        </div>
    </section>
    <section  class="px-24 py-20 flex">
        <div class=" w-1/2">
            <h6>Overview</h6>
            <h6>Kalih, Coffe, Tea & Spaces</h6>
            <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Assumenda nihil eum incidunt dolor unde repellendus, eveniet hic voluptas. Ea, ipsam.</p>
            <div class="flex">
                <div class="">
                    <h6>3452</h6>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. At, fugit!</p>
                </div>
                <div class="">
                    <h6>3452</h6>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. At, fugit!</p>
                </div>
                <div class="">
                    <h6>3452</h6>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. At, fugit!</p>
                </div>
            </div>
        </div>
        <div class=" w-1/2">

        </div>
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