<script>
import { ref } from "vue";
export default {
    props:{
        isopen:{
            type:Boolean,
            default:false,
        },
        handMenuClose:{
            type:Function,
            default:()=>{}
        }
    },
    setup(props){
        //0,730,1420,2670,3408,4132
        //0,500,1200,2300,3200,3900 
       
        window.addEventListener('scroll',()=>{
            if(window.scrollY < 500){
                home.value = true;
                about.value = false;
                work.value = false;
                skills.value = false;
                awards.value = false;
                contact.value = false;
            }else if(window.scrollY >= 500 && window.scrollY < 1200){
                home.value = false;
                about.value = true;
                work.value = false;
                skills.value = false;
                awards.value = false;
                contact.value = false;
            }else if(window.scrollY >= 1200 && window.scrollY < 2300){
                home.value = false;
                about.value = false;
                work.value = true;
                skills.value = false;
                awards.value = false;
                contact.value = false;
            }else if(window.scrollY >= 2300 && window.scrollY < 3200){
                home.value = false;
                about.value = false;
                work.value = false;
                skills.value = true;
                awards.value = false;
                contact.value = false;
            }else if(window.scrollY >= 3200 && window.scrollY < 3900){
                home.value = false;
                about.value = false;
                work.value = false;
                skills.value = false;
                awards.value = true;
                contact.value = false;
            }else if(window.scrollY >= 3900 ){
                home.value = false;
                about.value = false;
                work.value = false;
                skills.value = false;
                awards.value = false;
                contact.value = true;
            }
        })
        const scrollFn = (h)=>{
            document.body.scrollTop = h;
            document.documentElement.scrollTop = h;
            props.handMenuClose();
        }
        return {props, scrollFn};
    }
}
</script>
<template>
    <div id="sidebar" :class="{open:props.isopen}">
        <i class="fas fa-times" id="close" @click="props.handMenuClose"></i>
        <ul>
            <a href="javascript:;" @click="scrollFn(0)" :class="{focus:home,open:props.isopen}">HOME</a>
            <a href="./#about" @click="props.handMenuClose" :class="{focus:about,open:props.isopen}">ABOUT</a>
            <a href="./#work"  @click="props.handMenuClose" :class="{focus:work,open:props.isopen}">WORKS</a>
            <a href="./#skills" @click="props.handMenuClose" :class="{focus:skills,open:props.isopen}">SKILLS</a>
            <a href="./#awards" @click="props.handMenuClose" :class="{focus:awards,open:props.isopen}">AWARDS</a>
            <a href="./#contact" @click="props.handMenuClose" :class="{focus:contact,open:props.isopen}">CONTACT</a>
        </ul>
    </div>
</template>

<style lang="scss" scoped>
  $mainColor:#2b4749;
  $mainColor:#FE8696;
  $mainColor:#02377B;
    #sidebar{
        width:350px;
        height: 100vh;
        z-index: 9999999999999999;
        position: fixed;
        top: 0;
        right:-350px;
        background-color: #fff;
        transition: .3s;
        padding: 100px 50px;
        display: flex;
        flex-direction: column;
        &.open{
            right:0;
            transition: .3s;
        }
        >i{
            cursor: pointer;
            font-size: 35px;
            position: absolute;
            top: 40px;
            right:40px;
            transition: .3s;
            color:$mainColor;
            &:hover{
                color:#aaa;
                transition: .3s;
            }
        }
        >ul{
            list-style-type: none;
            >a{
                display: block;
                font-size: 20px;
                margin:30px 0;
                &.focus{
                    // color:$mainColor;
                    // font-weight: 600;
                }
                &.open1{
                    animation: openAmin calc((var(--i))*0.1)s linear;
                    @keyframes openAmin {
                        0%{
                            opacity: .1;
                            transform: translate(20px,50px);
                        }
                        100%{
                            opacity: 1;
                            transform: translate(0,0);
                        }
                    }
                }
            }
        }
    }
</style>