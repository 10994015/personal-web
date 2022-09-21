<script>
import {ref} from "vue";
export default {
    setup(){
        const view = ref(false);
        const timerNum = ref(1);
        setInterval(()=>{
            timerNum.value++;
            
            if(timerNum.value===10){
                view.value = !view.value;
            }
            if(timerNum.value>=10){
                timerNum.value = 1;
            }
        },1000)
        return {view};
    }
}
</script>
<template>
  <div id="banner">
      <img src="@/assets/images/about.jpg" v-show="view" class="bannerImg">
      <img src="@/assets/images/about2.jpg" v-show="!view" class="bannerImg">
      <div class="text open">
          <h2>Li-Cheng Yan</h2>
          <p>I come from Taoyuan</p>
          <a href="javascript:;">SEE MORE</a>
      </div>
  </div>
</template>

<style lang="scss" scoped>
    
   
    #banner{
        width:100%;
        height: 100vh;
        position: relative;
        img.bannerImg{
            width:50%;
            min-width:800px;
            height: 100%;
            object-fit: cover;
            border-radius: 100% 100% 100% 100% / 0% 0% 60% 0%;
            display: block;
            -webkit-filter:grayscale(.5);
            opacity: .9;
            animation:  view .5s  ;
            @keyframes view {
                0%{
                    opacity: .3;
                }
                100%{
                    opacity: .9;
                }
            }
            @media screen and (max-width:1260px){
                opacity: .5;
                width:100%;
                min-width: 0;
                @keyframes view {
                0%{
                    opacity: .1;
                }
                100%{
                    opacity: .5;
                }
            }
            }
        }
        >.text{
            position: absolute;
            background-color: transparent;
            top: 50%;
            left:60%;
            transform: translate(-50%,-50%);
            display: flex;
            flex-direction: column;
            align-items: flex-end;
             @media screen and (max-width:1260px){
                 left:10%;
                 transform: translate(0%,-50%);
                 align-items: flex-start;
             }
            &.open{
                animation: openText 1s ;
                @keyframes openText {
                    0%{
                        margin-top:60px;
                        opacity: 0;
                    }
                    100%{
                        margin-top:0;opacity: 1;
                        
                    }
                }
            }
            >h2{
                font-size: 70px;
                font-weight: 900;
                font-family: sans-serif;
                 @media screen and (max-width:600px){
                     font-size: 50px;
                 }
                  @media screen and (max-width:420px){
                     font-size: 40px;
                 }
                  @media screen and (max-width:320px){
                     font-size: 30px;
                 }
            }
            >p{
                font-size: 30px;
                color:#777;
                margin:10px 0;
                 @media screen and (max-width:1200px){
                     color:#000;
                 }
                  @media screen and (max-width:600px){
                     font-size: 24px;
                 }
                 @media screen and (max-width:320px){
                     font-size: 18px;
                 }
            }
            >a{
                display: block;
                text-align: center;
                line-height:56px ;
                border:2px #FE8696 solid;
                border-radius: 30px;
                font-size: 18px;
                width:180px;
                height: 60px;
                font-weight: 600;
                color:#FE8696;
                transition: .3s;
                margin-top: 30px;
                &:hover{
                    background-color: #FE8696;
                    color:#fff;
                    transition: .3s;
                }

            }
        }
    }
</style>