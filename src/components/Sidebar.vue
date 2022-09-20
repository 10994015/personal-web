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
        
        return {props};
    }
}
</script>
<template>
  <div id="sidebar" :class="{open:props.isopen}">
      <i class="fas fa-times" id="close" @click="props.handMenuClose"></i>
      <ul>
          <a href="javascript:;" class="focus">HOME</a>
          <a href="javascript:;">ABOUT</a>
          <a href="javascript:;">SKILLS</a>
          <a href="javascript:;">EDUCATION</a>
          <a href="javascript:;">WORK</a>
          <a href="javascript:;">OTHER</a>
          <a href="javascript:;">CONTACT</a>
      </ul>
  </div>
</template>

<style lang="scss" scoped>
    #sidebar{
        width:350px;
        height: 100vh;
        z-index: 999999;
        position: fixed;
        top: 0;
        right:-350px;
        background-color: #fff;
        transition: .3s;
        padding: 100px 50px;
        display: flex;
        flex-direction: column;
        border-left:1px #000 solid;
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
            color:#666;
            &:hover{
                color:#aaa;
                transition: .3s;
            }
        }
        >ul{
            list-style-type: none;
            >a{
                display: block;
                font-size: 21px;
                margin:30px 0;
                &.focus{
                    color:#f52f49;
                }
            }
        }
    }
</style>