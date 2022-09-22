<script>
import { ref} from "vue";
import Sidebar from "@/components/Sidebar.vue";
import Header from "@/components/Header.vue";
import Banner from "@/components/Banner.vue";
import About from "@/components/About.vue";
import Skills from "@/components/Skills.vue";
import Work from "@/components/Work.vue";
import Awards from "@/components/Awards.vue";
import Contact from "@/components/Contact.vue";
import Footer from "@/components/Footer.vue";
import Module from "@/components/Module.vue";
import ScrollTop from "@/components/ScrollTop.vue";
export default {
  components: {
    Sidebar,
    Header,
    Banner,
    About,
    Skills,
    Work,
    Awards,
    Contact,
    Footer,
    Module,
    ScrollTop
  },
  setup(){
    const isOpen = ref(false);
    const handMenuOpen = ()=>{
        isOpen.value = true;
    }
    const handMenuClose = ()=>{
      isOpen.value = false;
    }
    const isModule = ref(false);
    const isModuleSrc = ref('');
    const handOpenModule = (e)=>{
      isModule.value = true;
      isModuleSrc.value = e.target.src;
    }
    const handCloseModule = (e)=>{
      isModule.value = false;
      isModuleSrc.value = "";
    }
    return {isOpen, handMenuOpen, handMenuClose, isModule, handOpenModule, handCloseModule, isModuleSrc};
  }
}
</script>
<template>
  <Sidebar :isopen="isOpen" :handMenuClose="handMenuClose" />
  <Header :isopen="isOpen" :handMenuOpen="handMenuOpen" />
  <div id="main" :class="{darken:isOpen}">
      <Banner />
      <About />
      <Work />
      <Skills />
      <Awards :isModule="isModule" :handOpenModule="handOpenModule" />
      <Contact />
      <Footer /> 
      <Module :isModule="isModule" :handCloseModule="handCloseModule" :isModuleSrc="isModuleSrc" />
      <ScrollTop />
  </div>
</template>
<style lang="scss">
@import url(https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css);
@import url(https://fonts.googleapis.com/earlyaccess/cwtexyen.css);
@import url(https://fonts.googleapis.com/css?family=Raleway);
@import url(http://fonts.googleapis.com/earlyaccess/amstelvaralpha.css);
@import url(http://fonts.googleapis.com/earlyaccess/cabinvfbeta.css);
@import url(https://fonts.googleapis.com/earlyaccess/cwtexfangsong.css);
@import url(https://fonts.googleapis.com/earlyaccess/notosanstc.css);
@import url(https://fonts.googleapis.com/earlyaccess/cwtexming.css);
@import url(https://fonts.googleapis.com/earlyaccess/notosansjapanese.css);
  $mainColor :#678079;
  *{
    margin:0;
    padding: 0;
    box-sizing: border-box;
    background-color: #fff;
    scroll-behavior: smooth;
    font-family: 'cwTeXYen',raleway,sans-serif;
    font-family: 'Noto Sans Japanese',sans-serif;
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
