<script>
import { computed , onMounted, ref} from 'vue';
export default {
    props:{
        isModule:{
            type:Boolean,
            default:false,
        },
        handOpenModule:{
            type:Function,
            default:()=>{}
        }
    },
    setup(props){
        const isModule = computed(()=>{
            return props.isModule;
        })
        const handOpenModule = computed(()=>{
            return props.handOpenModule;
        })
        const screenH = screen.height;
        const isView = ref(false);
        onMounted(()=>{
            const h = document.getElementById('awards').offsetTop;
            console.log(h);
            
            window.addEventListener('scroll',()=>{
                if(window.scrollY >= (h- (screenH/2))){
                    isView.value = true;
                }
            })
        })
        
        return {isModule, handOpenModule, isView};
    }
}
</script>
<template>
  <div id="awards" :class="{view:isView}">
      <div class="awardsBox">
          <span @click="handOpenModule($event)" style="--i:1"><img src="@/assets/images/awards/01.jpg" alt=""></span>
          <span @click="handOpenModule($event)" style="--i:2"><img src="@/assets/images/awards/02.jpg" alt=""></span>
          <span @click="handOpenModule($event)" style="--i:3"><img src="@/assets/images/awards/03.jpg" alt=""></span>
          <span @click="handOpenModule($event)" style="--i:4"><img src="@/assets/images/awards/04.jpg" alt=""></span>
          <span @click="handOpenModule($event)" style="--i:5"><img src="@/assets/images/awards/05.jpg" alt=""></span>
          <span @click="handOpenModule($event)" style="--i:6"><img src="@/assets/images/awards/06.jpg" alt=""></span>
          <span @click="handOpenModule($event)" style="--i:7"><img src="@/assets/images/awards/07.jpg" alt=""></span>
          <span @click="handOpenModule($event)" style="--i:8"><img src="@/assets/images/awards/08.jpg" alt=""></span>
         
      </div>
  </div>
</template>
<style lang="scss" scoped>
$mainColor:#02377B;
    #awards{
        padding: 150px 0;
        width:100%;
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: #222;
        opacity: 0;
        &.view{
            animation: viewAnim .5s;
            opacity: 1;
            @keyframes viewAnim {
                0%{
                    opacity: 0;
                    transform: translateY(200px)
                }
                100%{
                    opacity: 1;
                    transform: translateY(0);
                }
            }
        }
        @media screen and (max-width:700px){
            min-height: 0;
        }
        >.myTitle{
            color:#fff;
            font-weight: 700;
            font-size: 24px;
            margin-bottom: 30px;
            display: block;
            text-align: center;
            background: transparent;
        }
        >.awardsBox{
            position: relative;
            widtH:200px;
            height: 250px;
            transform-style: preserve-3d;
            animation: animate 20s linear infinite;
            background: transparent;
            z-index: 0;
            @media screen and (max-width:700px){
                width:150px;
            }
            @media screen and (max-width:560px){
                width:120px;
            }
            @media screen and (max-width:433px){
                width:100px;
            }
            @keyframes animate {
                0%{
                    transform: perspective(1000px ) rotateY(0deg);
                }
                100%{
                    transform: perspective(1000px ) rotateY(360deg);
                }
            }
            >span{
                background: transparent;
                cursor: pointer;
                position: absolute;
                top: 0;
                left:0;
                widtH:100%;
                height: 100%;
                transform-origin: center;
                transform-style: preserve-3d;
                transform:rotateY(calc(var(--i)* 45deg)) translateZ(400px);
                -webkit-box-reflect: below 0px linear-gradient(transparent,transparent,#0004);
                z-index: 1;
                @media screen and (max-width:970px){
                    transform:rotateY(calc(var(--i)* 45deg)) translateZ(300px);
                }
                @media screen and (max-width:700px){
                    transform:rotateY(calc(var(--i)* 45deg)) translateZ(250px);
                }
                @media screen and (max-width:560px){
                    transform:rotateY(calc(var(--i)* 45deg)) translateZ(200px);
                }
                @media screen and (max-width:433px){
                    transform:rotateY(calc(var(--i)* 45deg)) translateZ(150px);
                }
                >img{
                    background: transparent;
                    position: absolute;
                    top:0;
                    left:0;
                    widtH:100%;
                    height: 100%;
                    object-fit: contain;
                    z-index: 1;
                }
            }
        }
    }
</style>