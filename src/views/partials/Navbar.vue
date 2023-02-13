<template>
    <nav id="navbar" class="navbar w-full flex px-[150px] py-[30px] max-lg:py-[20px] max-lg:px-[100px] gap-56 text-white" v-bind:class="[isSticky ? stickyClass : '']">
        <div class=" w-28 text-center">
            <RouterLink to="/">
                <h5>Samasta Boga Indonesia</h5>
            </RouterLink>
        </div>
        <div class="link flex justify-end gap-11 text-md py-2 px-14 text-base max-lg:px-1 max-md:px-1">
            <RouterLink to="/" class="a-link">Home</RouterLink>
            <RouterLink to="/about" class="a-link">About</RouterLink>
            <RouterLink to="/brand" class="a-link">The Brand</RouterLink>
            <a href="#footer" class="a-link">Career</a>
            <a href="#footer" class="a-link">Contacts</a>
        </div>
        <div class="menu p-2 text-lg " @click="mobile_menu = !mobile_menu">
            <font-awesome-icon :icon="[ 'fas', 'bars' ]" />
        </div>

        <div v-show="mobile_menu" class="active-menu">
            <RouterLink to="/kursus" class="a-link">Home</RouterLink>
            <RouterLink to="/about" class="a-link">About</RouterLink>
            <a href="#footer" class="a-link">The Brand</a>
            <RouterLink to="/kursus" class="a-link">Career</RouterLink>
            <RouterLink to="/about" class="a-link">Contacts</RouterLink>

        </div>
    </nav>
</template>

<script>

    export default{
        el: "#nav",
        data() {
            return {
                isSticky: false,
                stickyClass: 'is_sticky',
                scrollPosition: 0,
                show: false,
                course : '',
                mobile_menu : false

            }
        },
        created () {
                window.addEventListener('scroll', this.handleScroll)
        },
        destroyed () {
                window.removeEventListener('scroll', this.handleScroll);
        },
        methods:{
            handleScroll(event){
                this.scrollPosition = window.scrollY
                    if(this.scrollPosition > 0){
                            this.isSticky=true
                        }else{
                            this.isSticky=false
                        }
            },

        }
        }
        

</script>

<style scoped>

    *{
        margin: 0;   
    }

    nav.is_sticky{
        position: fixed;
        top: 0;
        color: black;
        background-color: rgba(214,214,214,0.90);
        z-index: 10;
        height: 100px;
        -webkit-animation: .95s ease-in-out 0s normal none 1 running fadeInDown;
        animation: .95s ease-in-out 0s normal none 1 running fadeInDown;
        -webkit-transition: all 0.3s cubic-bezier(0.645, 0.045, 0.355, 1);
        transition: all 0.3s cubic-bezier(0.645, 0.045, 0.355, 1);
        -webkit-box-shadow: 0 8px 20px 0 rgba(0, 0, 0, 0.1);
        box-shadow: 0 8px 20px 0 rgba(0, 0, 0, 0.1);
    }

    
    nav a:hover{
        color: #e01c5c;
    }

    .a-link::after{
        margin-top: 10px;
        content: '';
        display: block;
        width: 0;
        height: 1.5px;
        background: white;
        transition: width .3s;
    }


    a.a-link:hover:after{
        width: 100%;
    }

    .menu{
        display: none;
        cursor: pointer;
    }

    .active-menu{
        background-color: white;
        position: absolute;
        right: 0;
        top: 100px;
        width: 200px;
        padding: 20px;
        border-radius: 10px;
    }



    a.a-link.router-link-exact-active::after {
        width: 100%;
    }

    a.a-link.router-link-exact-active{
        color: #af9552;
    }

    @media only screen and (max-width: 640px){
            nav{
                padding: 30px;
            }

            .link{
                display: none;
            }

            .menu{
                display: block;
            }






            
        }
</style>