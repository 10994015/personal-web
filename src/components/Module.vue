<script>
import { computed } from 'vue';
export default {
    props:{
        isModule:{
            type:Boolean,
            default:false,
        },
        isModuleSrc:{
            type:String,
            default:""
        },
        handCloseModule:{
            type:Function,
            default:()=>{}
        }
    },
    setup(props){
         const isModule = computed(()=>{
            return props.isModule;
        })
        const isModuleSrc = computed(()=>{
            return props.isModuleSrc;
        })
        const handCloseModule = computed(()=>{
            return props.handCloseModule;
        })
        return { isModule, isModuleSrc, handCloseModule };
    }
}
</script>
<template>
  <div id="module" v-show="isModule">
      <div class="imgBox">
          <i class="fas fa-times" id="close" @click="handCloseModule"></i>
          <!-- <img :src="require('@/assets/images/awards/'+isModuleSrc)" alt=""> -->
          <img :src="isModuleSrc" alt="">
      </div>
  </div>
</template>
<style lang="scss" scoped>
    #module{
        position: fixed;
        top: 0;
        left:0;
        z-index: 999999;
        width:100%;
        height: 100vh;
        background-color:rgba(0,0,0,.5);
        display: flex;
        justify-content: center;
        align-items: center;
        animation: open .5s ;
        @keyframes open {
            0%{
                opacity: 0;
            }
            100%{
                opacity: 1;
            }
        }
        >.imgBox{
            height: 85%;
            max-width:1200px;
            border:8px #fff solid;
            position: relative;
            @media screen and (max-width:1200px){
                max-width: 800px;
                height: auto;
                width:90%;
            }
            >i{
                position: absolute;
                top: 10px;
                right: 15px;
                cursor: pointer;
                font-size: 30px;
                color:#000;
                background-color: transparent;
            }
            >img{
                height: 100%;
                width:auto;
                object-fit: cover;
                @media screen and (max-width:1200px){
                    width: 100%;
                    height: auto;
                }
            }
        }
    }
</style>