
<script>
import {ref } from "vue";
export default {
    props:{
        isopen:{
            type:Boolean,
            default:false,
        },
        handMenuOpen:{
            type:Function,
            default:()=>{}
        }
    },
    setup(props){
        console.log(props);
        
        return {props};
    }
}
</script>
<template>
  <header id="header">
      <a href="javascript:;" id="logo">LiChengYan</a>
      <i class="fas fa-bars" id="menu" @click="props.handMenuOpen"></i>
  </header>
</template>

<style lang="scss" scoped>
    header#header{
        position: fixed;
        top: 0;
        left:0;
        width:100%;
        height: 80px;
        box-shadow: 0px 0px 5px 3px #ddd;
        padding:0 250px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        z-index: 99999;
        @media screen and (max-width:1400px){
            padding:0 150px;
        }
        @media screen and (max-width:940px){
            padding:0 60px;
        }
        @media screen and (max-width:550px){
            padding:0 35px;
        }
        @media screen and (max-width:320px){
            padding:0 20px;
        }
        >a#logo{
            color:#333;
            font-weight: 900;
            font-size: 28px;
            font-style:italic; 
            font-family: 'cwTeXYen', sans-serif;
            @media screen and (max-width:550px){
                font-size: 20px;
            }
        }
        >i#menu{
            font-size: 28px;
            cursor: pointer;
        }
    }
</style>