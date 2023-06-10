<script>
import { parseStringStyle } from '@vue/shared';


export default {
    data(){
        return {
            mobile: false,
            scrolled : false,
            windowWidth: false,
            mobileNav: false,
            activePage: false,
        }
    },
    methods:{
        checkScreen(){
            this.windowWidth = window.innerWidth
            if (this.windowWidth <= 750) {
                this.mobile = true;
                return;
            }
            this.mobile = false;
            return;
        },
        toggleMobileNav(){
            this.mobileNav = !this.mobileNav;
        },
        
    },
    created(){
        window.addEventListener('resize', this.checkScreen);
        this.checkScreen();

        
       
    },
    mounted(){
        const links = document.querySelectorAll('li a')
        links.forEach(link => {
            link.addEventListener('click', (e) => {
                links.forEach((link) => {
                    link.classList.remove('active');
                });
                e.preventDefault();
                link.classList.add('active');
            });
        });
    }
}

</script>

<template>

    <nav class=" z-50 bg-[#141414] font-lato w-[100vw] h-[3.8rem] sticky top-0
    flex items-center justify-between text-orange-500 shadow-xl
    ">
           <svg class="w-10 ml-20" viewBox="0 0 1024 1024" xmlns="http://www.w3.org/2000/svg"><path fill="#ffa500" d="M128 352.576V352a288 288 0 0 1 491.072-204.224 192 192 0 0 1 274.24 204.48 64 64 0 0 1 57.216 74.24C921.6 600.512 850.048 710.656 736 756.992V800a96 96 0 0 1-96 96H384a96 96 0 0 1-96-96v-43.008c-114.048-46.336-185.6-156.48-214.528-330.496A64 64 0 0 1 128 352.64zm64-.576h64a160 160 0 0 1 320 0h64a224 224 0 0 0-448 0zm128 0h192a96 96 0 0 0-192 0zm439.424 0h68.544A128.256 128.256 0 0 0 704 192c-15.36 0-29.952 2.688-43.52 7.616 11.328 18.176 20.672 37.76 27.84 58.304A64.128 64.128 0 0 1 759.424 352zM672 768H352v32a32 32 0 0 0 32 32h256a32 32 0 0 0 32-32v-32zm-342.528-64h365.056c101.504-32.64 165.76-124.928 192.896-288H136.576c27.136 163.072 91.392 255.36 192.896 288z"/></svg>

            <ul @click="dre" v-show="!mobile" class=" flex justify-around w-[50%] lg:w-[40%] mr-10 uppercase text-[0.9rem] font-mono ">
                <li ><router-link class="home" to="/">Beranda</router-link></li>
                <li >Penawaran</li>
                <li  ><router-link class="contacts" to="/contacts">Kontak</router-link></li>
                <li > <router-link class="about" to="/#about">Tentang</router-link> </li>
            </ul>
            
            <svg @click="toggleMobileNav" :class="{ 'icon-active': mobileNav }" class=" transition-all duration-200 w-10 mr-5 " fill="#FFA500" v-show="mobile" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path d="M19 13C19.5523 13 20 12.5523 20 12C20 11.4477 19.5523 11 19 11C18.4477 11 18 11.4477 18 12C18 12.5523 18.4477 13 19 13Z" stroke="#000000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M12 13C12.5523 13 13 12.5523 13 12C13 11.4477 12.5523 11 12 11C11.4477 11 11 11.4477 11 12C11 12.5523 11.4477 13 12 13Z" stroke="#000000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M5 13C5.55228 13 6 12.5523 6 12C6 11.4477 5.55228 11 5 11C4.44772 11 4 11.4477 4 12C4 12.5523 4.44772 13 5 13Z" stroke="#000000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
    </nav>
    <transition name="slide-fade">
         <ul id="dropdownNav" class=" fixed w-[100vw] z-40 top-10 text-orange-500 py-8  bg-[#141414] flex flex-col gap-4 font-lato items-center text-[2rem] " v-show="mobileNav">
            <li>Beranda</li>
            <li>Penawaran</li>
            <li>Kontak</li>
            <li>Tentang</li>
        </ul>
    </transition>
</template>
<style>
#dropdownNav li {
    @apply hover:bg-orange-300 w-[80%] rounded-lg text-center py-4 uppercase;
}
.icon-active {
    @apply rotate-180 transition-all duration-200;
}
.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translatey(20px);
  opacity: 0;
}

.active {
    background-color: brown;
}

</style>