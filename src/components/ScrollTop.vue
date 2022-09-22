
<script>
import {ref} from "vue";
export default {
    setup(){
        const toTop = ()=>{
            document.body.scrollTop = 0;
            document.documentElement.scrollTop = 0;
        }
        const toTopView = ref(false);
        window.addEventListener('scroll',()=>{
            if(window.scrollY > 500 ){
                toTopView.value = true;
            }else{
                toTopView.value = false;
            }
        })
        return {toTop, toTopView};
    }
}
</script>
<template>
<Transition name="v">

  <div id="scrollTop" @click="toTop" v-show="toTopView" :class="{view:toTopView}">
    <svg xmlns="http://www.w3.org/2000/svg"  fill="currentColor" class="bi bi-chevron-up" viewBox="0 0 16 16">
    <path fill-rule="evenodd" d="M7.646 4.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1-.708.708L8 5.707l-5.646 5.647a.5.5 0 0 1-.708-.708l6-6z"/>
    </svg>
  </div>
 </Transition>
 
</template>

<style lang="scss" scoped>
 $mainColor:#02377B;
    .v-enter-active,
    .v-leave-active {
        transition: all 0.3s ease;
    }

    .v-enter-from{
        transform: translateX(30px);
        opacity: .5;
    }
    .v-enter-to{
        transform: translateX(0);
        opacity: 1;
    }
    .v-leave-from {
        transform: translateX(0);
        opacity: 1;
    }
    .v-leave-to {
        transform: translateX(30px);
        opacity: 0;
    }
    #scrollTop{
        position: fixed;
        bottom:40px;
        right:30px;
        background-color:  $mainColor;
        display: flex;
        justify-content: center;
        align-items: center;
        widtH:60px;
        height: 60px;
        cursor: pointer;
        border-radius:50%;
        transition: .3s;
        
        &:hover{
            background-color:#002049;
        }
        >svg{
            background: transparent;
            transition: .5s;
            color:#fff;
            width:30px;
            height: 30px;
        }
    }
</style>