<script>
import { ref, computed } from "vue";
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
       
        
        const handMenuClose = computed(()=>{
            return props.handMenuClose;
        })
        return {handMenuClose,props };
    }
}
</script>
<template>
    <div id="sidebar" :class="{open:props.isopen}">
        <i class="fas fa-times" id="close" @click="handMenuClose"></i>
        <ul>
            <a href="./#banner" @click="handMenuClose" :class="{focus:home,open:props.isopen}">HOME</a>
            <a href="./#about" @click="handMenuClose" :class="{focus:about,open:props.isopen}">ABOUT</a>
            <a href="./#work"  @click="handMenuClose" :class="{focus:work,open:props.isopen}">WORKS</a>
            <a href="./#skills" @click="handMenuClose" :class="{focus:skills,open:props.isopen}">SKILLS</a>
            <a href="./#awards" @click="handMenuClose" :class="{focus:awards,open:props.isopen}">AWARDS</a>
            <a href="./#contact" @click="handMenuClose" :class="{focus:contact,open:props.isopen}">CONTACT</a>
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