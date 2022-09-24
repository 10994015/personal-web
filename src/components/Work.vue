<script>
import {reactive, ref,onMounted } from "vue";
export default {
    props:{
       
    },
    setup(){
        const wordArr = reactive([
            {
                url:"https://www.ice-finland.club/",
                src:require('@/assets/images/colorful.jpg'),
                name:'冰芬文教',
                content:'為冰芬文教架設形象網站'
            },
            {
                url:"https://www.ice-finland.club/cms",
                src:require('@/assets/images/colorfulcms.jpg'),
                name:'冰芬文教後台管理系統',
                content:'使用PHP架構冰芬文教後台管理系統'
            },
            {
                url:"https://adsarousal.com/",
                src:require('@/assets/images/ads.jpg'),
                name:'碩士論文問卷系統',
                content:'使用PHP製作論文用問卷系統'
            },
            {
                url:"https://10994015.github.io/7zip/start.html",
                src:require('@/assets/images/seven.jpg'),
                name:'七大罪遊戲',
                content:'製作七大原罪網頁小遊戲'
            },
            {
                url:"https://www.evoneic.com/",
                src:require('@/assets/images/evone.jpg'),
                name:'憶旺智慧股份有限公司',
                content:'架設憶旺智慧公司形象網站'
            },
            {
                url:"https://carboncst.com/",
                src:require('@/assets/images/cst.jpg'),
                name:'臺灣碳材料學會CST',
                content:'使用PHP架設臺灣碳材料學會前台與後台管理'
            },
            
            {
                url:"https://jiousaio.com/",
                src:require('@/assets/images/jiousaio.jpg'),
                name:'九霄空間設計JIOUSIAO',
                content:'架設九霄空間設計形象網站'
            },
            {
                url:"https://jiousaioshop.com/",
                src:require('@/assets/images/jiousaioshop.jpg'),
                name:'九霄模型',
                content:'使用WordPress架設模型購物網站'
            },
            {
                url:"https://jiousaio.com/marvel/",
                src:require('@/assets/images/marvel.jpg'),
                name:'中原大學衛保組漫威遊戲',
                content:'與中原大學衛保組合作製作網頁小遊戲及後台管理'
            },
            {
                url:"https://jiousaio.com/Lecture/",
                src:require('@/assets/images/lecture.jpg'),
                name:'中原大學衛保組魷魚遊戲',
                content:'與中原大學衛保組合作製作網頁小遊戲及後台管理'
            },
           
            {
                url:"https://10994015.github.io/tripleE/",
                src:require('@/assets/images/yikang.jpg'),
                name:'益康診所APP',
                content:'與益康診所合作架設診所關愛APP'
            },
            
            {
                url:"https://lichengyanchala.zyrosite.com/",
                src:require('@/assets/images/doll.jpg'),
                name:'公仔網頁',
                content:'使用Zyro製作簡單公仔網頁'
            },
        ])
        const workItem = ref(null);
        
        const screenH = screen.height;
        const isView = ref(false);
        onMounted(()=>{
            const h = document.getElementById('work').offsetTop;
            console.log(h);
            
            window.addEventListener('scroll',()=>{
                if(window.scrollY >= (h- (screenH/2))){
                    isView.value = true;
                }
            })
        })
       
        
        return {wordArr, workItem, isView };
    }
}
</script>
<template>
  <div id="work" :class="{view:isView}">
    <span class="myTitle">MY WORK</span>
     <div class="workDiv">
       
         <div class="workBox">
            <a :href="item.url" target="_blank" class="workItem" ref="workItem" v-for="item in wordArr" :key="item.name">
                <img :src="item.src" alt="">
                <h2>{{item.name}}</h2>
                <p> {{item.content}} </p>
            </a>
        </div>
     </div>
  </div>
</template>
<style lang="scss" scoped>
$mainColor:#213558;
    #work{
        padding: 100px 0;
        width:100%;
        // max-width:1200px;
        // background-image: linear-gradient(to bottom,#FFB896,#FE8696,#FFB896,#FE8696);
        // background-image: url('~@/assets/images/bg2.jpg');
        background-image: radial-gradient(circle at center,#008081,#142D6A);
        opacity: 0;
        // background-color: #213558;
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
        >.myTitle{
            color:#fff;
            font-weight: 700;
            font-size: 24px;
            margin-bottom: 50px;
            display: block;
            text-align: center;
            background: transparent;
        }
        >.workDiv{
            width:100%;
            max-width:1100px;
            margin:0 auto;
            position: relative;
            background-color: transparent;
           
            >.workBox{
                width:100%;
                max-width:1100px;
                margin:0 auto;
                display: grid;
                grid-template-columns: repeat(4,250px);
                background-color: transparent;
                justify-content: center;
                height: auto;
                grid-column-gap: 25px;
                grid-row-gap: 2em;
                @media screen and (max-width:1200px){
                    grid-template-columns: repeat(3,250px);
                }
                @media screen and (max-width:1200px){
                    grid-template-columns: repeat(2,280px);
                }
                @media screen and (max-width:600px){
                    grid-template-columns: repeat(2,250px);
                }
                @media screen and (max-width:535px){
                    grid-template-columns: repeat(1,300px);
                }
                @media screen and (max-width:340px){
                    grid-template-columns: repeat(1,85%);
                }
                >.workItem{
                    // background-image: linear-gradient(to bottom,#FFAE96,#FE8696,#FFAE96,#FE8696);
                    background-color: rgba(255,255,255,.3);
                    // border-radius: 10px;
                    padding: 30px 15px;
                    display: flex;
                    flex-direction: column;
                    align-items: center;
                    box-shadow: 0 2px 15px rgb(2, 41, 78);
                    backdrop-filter:blur(10px);
                    transition: .5s;
                    width:100%;
                    
                    &:hover{
                        background-color: rgba(255,255,255,.4);
                        background-color: rgba(255,255,255,.65);
                        >h2{
                            color:#011631;
                        }
                        >p{
                            color:#011631;
                        }
                    }
                    
                    >img{
                        width:150px;
                        height: 150px;
                        border-radius: 50%;
                        object-fit: cover;
                        border:4px #fff solid;
                        margin-bottom: 15px;
                    }
                    >h2{
                        color:#fff;
                        font-size:18px;
                        margin-bottom: 15px;
                        text-align: center;
                        transition: .5s;
                        font-weight: 500;
                    }
                    >p{
                        color:#ddd;
                        transition: .5s;
                        text-align: center;
                        font-size: 14px;
                    }
                }
            }
        }
        
    }
</style>