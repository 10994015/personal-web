<script>
import { ref} from "vue";
import Sidebar from "@/components/Sidebar.vue";
import Header from "@/components/Header.vue";
import Banner from "@/components/Banner.vue";
export default {
  components: {
    Sidebar,
    Header,
    Banner,
  },
  setup(){
    const isOpen = ref(false);
    const handMenuOpen = ()=>{
        isOpen.value = true;
    }
    const handMenuClose = ()=>{
      isOpen.value = false;
    }
    return {isOpen, handMenuOpen, handMenuClose};
  }
}
</script>
<template>
  <Sidebar :isopen="isOpen" :handMenuClose="handMenuClose" />
  <div id="main" :class="{darken:isOpen}">
    <Header :isopen="isOpen" :handMenuOpen="handMenuOpen" />
    <Banner />
  </div>
</template>
<style lang="scss">
@import url(https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css);
@import url(https://fonts.googleapis.com/earlyaccess/cwtexyen.css);
@import url(https://fonts.googleapis.com/css?family=Raleway);
@import url(http://fonts.googleapis.com/earlyaccess/amstelvaralpha.css);
@import url(http://fonts.googleapis.com/earlyaccess/cabinvfbeta.css);
  *{
    margin:0;
    padding: 0;
    box-sizing: border-box;
    background-color: #fff;
    font-family: 'cwTeXYen',raleway,sans-serif;
  }
  a{
    color:#111;
    text-decoration: none;
  }
  h1,h2,h3,h4,h5,h6,p,a{
    background-color: transparent;
  }
  #main{
    transition: .5s;
    &.darken{
      -webkit-filter:brightness(.5);
      transition: .5s;
    }
  }
  
</style>
