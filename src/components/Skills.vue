<script>
import {ref, reactive} from "vue";
export default {
    setup(){
        const skills = reactive([
            {
                name:"HTML5",
                percent:90,
            },
            {
                name:"CSS3",
                percent:90,
            },
            {
                name:"JavaScript",
                percent:85,
            },
            {
                name:"PHP",
                percent:90,
            },
            {
                name:"MySQL",
                percent:75,
            },
            {
                name:"Vue",
                percent:70,
            },
            {
                name:"Python",
                percent:75,
            },
            {
                name:"Git&GitHub",
                percent:90,
            },
            
        ])
        const expriences = reactive([
            {
                name:"中原大學碩士班",
                time:"2020-2022"
            },
            {
                name:"憶旺智慧工程師",
                time:"2021-2022"
            },
            {
                name:"中原大學程式設計講師",
                time:"2021-2022"
            },
            {
                name:"Python程式設計家教",
                time:"2021"
            },

            {
                name:"中原大學多媒體程式設計助教",
                time:"2021-2022"
            },
            {
                name:"中原大學Python程式設計助教",
                time:"2021-2022"
            },
            {
                name:"李紹陽數學輔導老師",
                time:"2020-2021"
            },
            {
                name:"三星samsung活動督導",
                time:"2019-2020"
            },
        ])
        return {skills, expriences};
    }
}
</script>
<template>
  <div id="skills">
      <span class="myTitle">MY expriences & SKILLS</span>
        <div class="content">
            <div class="expriences">
                <!-- <div class="timeline"></div> -->
                <div class="content">
                    <div class="item" v-for="item in expriences" :key="item.name">
                        <li>{{item.name}}</li>
                        <p>{{item.time}}</p>
                    </div>
                </div>
            </div>
            <div class="skillsBox">
                <div class="skillsItem" v-for="item in skills" :key="item.name">
                    <div class="title"><p class="name">{{item.name}}</p><p class="percent">{{item.percent}}%</p> </div>
                    <div class="skillsBar">
                        <div class="bar" :style="{width:item.percent + '%'}"></div> 
                    </div>
                </div>
            
            </div>
            
        </div>
  </div>
</template>

<style lang="scss" scoped>
  $mainColor:#FE8696;
  $mainColor:#02377B;
    #skills{
        padding: 50px 0 100px;
        width:100%;
        max-width:1200px;
        margin: 0 auto;
        >.myTitle{
            color:$mainColor;
            font-weight: 700;
            font-size: 24px;
            margin-bottom: 50px;
            display: block;
            text-align: left;
            text-transform: uppercase;
            max-width: 1000px;
            display: block;
            width:100%;
            margin:0 auto 30px;
            position: relative;
            padding: 10px 0;
            @media screen and (max-width:1050px){
                
                padding: 10px 30px;
            }
            @media screen and (max-width:675px){
                text-align: center;
            }
            &::before{
                content:"";
                position: absolute;
                bottom: 0;
                left:0;
                width:100px;
                height: 3px;
                background-color: #aaa;
                // @media screen and (max-width:1050px){
                //     left:50%;
                //     transform: translateX(-50%);
                // }
                @media screen and (max-width:1050px){
                    // text-align: center;
                    left:30px;
                }
                @media screen and (max-width:675px){
                    left:50%;
                    transform: translateX(-50%);
                }
            }
        }
        >.content{
            display: flex;
            justify-content: center;
            @media screen and (max-width:675px){
                flex-direction: column;
                align-items: center;
                justify-content: flex-start;
            }
            >.skillsBox{
                display: grid;
                width:450px;
                grid-template-columns: repeat(1, 450px);
                grid-row-gap: 0;
                justify-content: center;
                margin-right: 20px;
                @media screen and (max-width:1050px){
                   width:400px;
                    grid-template-columns: repeat(1, 350px);
                }
                @media screen and (max-width:675px){
                    margin-right: 0;
                    grid-row-gap: 20px;
                }
                @media screen and (max-width:450px){
                    width:100%;
                    grid-template-columns: repeat(1, 85%);
                }
                >.skillsItem{
                    margin-bottom: 0;
                    >.title{
                        margin-bottom: 5px;
                        display: flex;
                        justify-content: flex-end;
                        >p{
                            margin-left:15px;
                        }

                    }
                    >.skillsBar{
                        width:100%;
                        height: 13px;
                        background-color: #ddd;
                        // border-radius: 15px;
                        overflow: hidden;
                        >.bar{
                            width:80%;
                            height: 13px;
                            background-image: linear-gradient(to right,rgb(73, 121, 184),#02377B);
                            // border-radius: 15px;
                            animation: run 1.5s ;
                            @keyframes run {
                                0%{
                                    width:0%;
                                }
                                
                            }
                        }
                    }
                }
            }
            >.expriences{
                width:500px;
                margin-left: 20px;
                display: flex;
                @media screen and (max-width:1050px){
                    width:400px;
                }
                @media screen and (max-width:675px){
                    justify-content: center;
                    margin-left: 0;
                    width:100%;
                    padding: 0 15px;
                }
                >.timeline{
                    width:5px;
                    height: 100%;
                    background-color: #ccc;
                    margin-right: 40px;
                }
                >.content{
                    padding: 20px 0;
                   >.item{
                       margin-bottom:12px;
                       >li{
                           font-size: 18px;
                           font-weight: 700;
                       }
                        >p{
                            font-size: 15px;
                            color:#888;
                            margin-top: 3px;
                            margin-left: 30px;
                        }
                   }
                }
               
            }
        }
        
    }
</style>