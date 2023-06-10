<template>

    <h2 class=" text-orange-500 font-aurora text-[3rem] text-center  mt-[3rem]">Our Top Menu</h2>
    <p class="text-white font-mono text-center mb-7">Special For Make Your Day Happy</p>
    <div class=" flex font-mono justify-center gap-2 w-[80%] mx-auto flex-wrap gap-4 ">
        
        <div class="item">
            <div class="bg-[url('/image/item-1.jpg')] "></div>
            <h3>Oyster Soup</h3>
            <p>150 K</p>
        </div>

        <div class="item">
                <div class="bg-[url('/image/item-2.jpg')] "></div>
                <h3>Fried Salmon</h3>
                <p>150 K</p>
        </div>

        <div class="item">
                    <div class="bg-[url('/image/item-3.jpg')] "></div>
                    <h3>Fried Lobster</h3>
                    <p>150 K</p>
        </div>

        <div class="item">
                        <div class="bg-[url('/image/item-4.jpg')] "></div>
                        <h3>Fried Lobster</h3>
                        <p>150 K</p>
            </div>
        <div class="item">
             <div class="bg-[url('/image/item-5.jpg')] "></div>
             <h3>Fried Lobster</h3>
             <p>150 K</p>
        </div>

        <div class="item">
              <div class="bg-[url('/image/item-6.jpg')] "></div>
             <h3>Fried Kerrang</h3>
              <p>150 K</p>
        </div>
       
    </div>
</template>
<style>
    .item {
        @apply w-[15rem] h-[14rem] flex flex-col cursor-pointer hover:bg-black hover:bg-opacity-50 ;
    }
    .item div {
        @apply bg-cover bg-no-repeat bg-center h-[10rem];
    }
    .item h3 {
        @apply text-[1.2rem] text-orange-500 text-center;
    }
    .item p{
        @apply text-white text-center;
    }
</style>
