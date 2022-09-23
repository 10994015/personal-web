<script>
import {ref} from "vue";
export default {
    setup(){
        
        return {};
    }
}
</script>
<template>


  <div id="about">
      <div class="imgBox">
          <img src="@/assets/images/about5.jpg" class="aboutImg">
      </div>
      <div class="content">
          <span class="myTitle">MY INTRO</span>
          <h2 class="aboutMe">About Me</h2>
          <ul class="intro">
              <li>熱愛嘗試新的事物</li>
              <li>善於溝通和分享新知</li>
              <li>具備開放積極的特質</li>
          </ul>
          <div class="basic"><p class="question">姓名:</p><p class="answer">李承諺(Li-Cheng Yan)</p></div>
          <div class="basic"><p class="question">出生日期:</p><p class="answer">1997/08/22</p></div>
          <div class="basic"><p class="question">家鄉:</p><p class="answer">桃園市桃園區</p></div>
          <div class="basic"><p class="question">電子郵件:</p><p class="answer">a0938599191@gmail.com</p></div>
          <div class="basic"><p class="question">手機號碼:</p><p class="answer">0938599191</p></div>
          <!-- <div class="interest"></div> -->
          <div class="icon">
              <a href="https://www.facebook.com/profile.php?id=100002935953804">
                <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" fill="currentColor" class="bi bi-facebook" viewBox="0 0 16 16">
                    <path d="M16 8.049c0-4.446-3.582-8.05-8-8.05C3.58 0-.002 3.603-.002 8.05c0 4.017 2.926 7.347 6.75 7.951v-5.625h-2.03V8.05H6.75V6.275c0-2.017 1.195-3.131 3.022-3.131.876 0 1.791.157 1.791.157v1.98h-1.009c-.993 0-1.303.621-1.303 1.258v1.51h2.218l-.354 2.326H9.25V16c3.824-.604 6.75-3.934 6.75-7.951z"/>
                </svg>
              </a>
              <a href="https://www.instagram.com/14___2/">
                  <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" fill="currentColor" class="bi bi-instagram" viewBox="0 0 16 16">
                    <path d="M8 0C5.829 0 5.556.01 4.703.048 3.85.088 3.269.222 2.76.42a3.917 3.917 0 0 0-1.417.923A3.927 3.927 0 0 0 .42 2.76C.222 3.268.087 3.85.048 4.7.01 5.555 0 5.827 0 8.001c0 2.172.01 2.444.048 3.297.04.852.174 1.433.372 1.942.205.526.478.972.923 1.417.444.445.89.719 1.416.923.51.198 1.09.333 1.942.372C5.555 15.99 5.827 16 8 16s2.444-.01 3.298-.048c.851-.04 1.434-.174 1.943-.372a3.916 3.916 0 0 0 1.416-.923c.445-.445.718-.891.923-1.417.197-.509.332-1.09.372-1.942C15.99 10.445 16 10.173 16 8s-.01-2.445-.048-3.299c-.04-.851-.175-1.433-.372-1.941a3.926 3.926 0 0 0-.923-1.417A3.911 3.911 0 0 0 13.24.42c-.51-.198-1.092-.333-1.943-.372C10.443.01 10.172 0 7.998 0h.003zm-.717 1.442h.718c2.136 0 2.389.007 3.232.046.78.035 1.204.166 1.486.275.373.145.64.319.92.599.28.28.453.546.598.92.11.281.24.705.275 1.485.039.843.047 1.096.047 3.231s-.008 2.389-.047 3.232c-.035.78-.166 1.203-.275 1.485a2.47 2.47 0 0 1-.599.919c-.28.28-.546.453-.92.598-.28.11-.704.24-1.485.276-.843.038-1.096.047-3.232.047s-2.39-.009-3.233-.047c-.78-.036-1.203-.166-1.485-.276a2.478 2.478 0 0 1-.92-.598 2.48 2.48 0 0 1-.6-.92c-.109-.281-.24-.705-.275-1.485-.038-.843-.046-1.096-.046-3.233 0-2.136.008-2.388.046-3.231.036-.78.166-1.204.276-1.486.145-.373.319-.64.599-.92.28-.28.546-.453.92-.598.282-.11.705-.24 1.485-.276.738-.034 1.024-.044 2.515-.045v.002zm4.988 1.328a.96.96 0 1 0 0 1.92.96.96 0 0 0 0-1.92zm-4.27 1.122a4.109 4.109 0 1 0 0 8.217 4.109 4.109 0 0 0 0-8.217zm0 1.441a2.667 2.667 0 1 1 0 5.334 2.667 2.667 0 0 1 0-5.334z"/>
                  </svg>
              </a>
              <a href="https://line.me/ti/p/jm4Sa6RLqK">
                  <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" fill="currentColor" class="bi bi-line" viewBox="0 0 16 16">
                    <path d="M8 0c4.411 0 8 2.912 8 6.492 0 1.433-.555 2.723-1.715 3.994-1.678 1.932-5.431 4.285-6.285 4.645-.83.35-.734-.197-.696-.413l.003-.018.114-.685c.027-.204.055-.521-.026-.723-.09-.223-.444-.339-.704-.395C2.846 12.39 0 9.701 0 6.492 0 2.912 3.59 0 8 0ZM5.022 7.686H3.497V4.918a.156.156 0 0 0-.155-.156H2.78a.156.156 0 0 0-.156.156v3.486c0 .041.017.08.044.107v.001l.002.002.002.002a.154.154 0 0 0 .108.043h2.242c.086 0 .155-.07.155-.156v-.56a.156.156 0 0 0-.155-.157Zm.791-2.924a.156.156 0 0 0-.156.156v3.486c0 .086.07.155.156.155h.562c.086 0 .155-.07.155-.155V4.918a.156.156 0 0 0-.155-.156h-.562Zm3.863 0a.156.156 0 0 0-.156.156v2.07L7.923 4.832a.17.17 0 0 0-.013-.015v-.001a.139.139 0 0 0-.01-.01l-.003-.003a.092.092 0 0 0-.011-.009h-.001L7.88 4.79l-.003-.002a.029.029 0 0 0-.005-.003l-.008-.005h-.002l-.003-.002-.01-.004-.004-.002a.093.093 0 0 0-.01-.003h-.002l-.003-.001-.009-.002h-.006l-.003-.001h-.004l-.002-.001h-.574a.156.156 0 0 0-.156.155v3.486c0 .086.07.155.156.155h.56c.087 0 .157-.07.157-.155v-2.07l1.6 2.16a.154.154 0 0 0 .039.038l.001.001.01.006.004.002a.066.066 0 0 0 .008.004l.007.003.005.002a.168.168 0 0 0 .01.003h.003a.155.155 0 0 0 .04.006h.56c.087 0 .157-.07.157-.155V4.918a.156.156 0 0 0-.156-.156h-.561Zm3.815.717v-.56a.156.156 0 0 0-.155-.157h-2.242a.155.155 0 0 0-.108.044h-.001l-.001.002-.002.003a.155.155 0 0 0-.044.107v3.486c0 .041.017.08.044.107l.002.003.002.002a.155.155 0 0 0 .108.043h2.242c.086 0 .155-.07.155-.156v-.56a.156.156 0 0 0-.155-.157H11.81v-.589h1.525c.086 0 .155-.07.155-.156v-.56a.156.156 0 0 0-.155-.157H11.81v-.589h1.525c.086 0 .155-.07.155-.156Z"/>
                  </svg>
              </a>
              <a href="https://github.com/10994015">
                 <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" fill="currentColor" class="bi bi-github" viewBox="0 0 16 16">
                    <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.012 8.012 0 0 0 16 8c0-4.42-3.58-8-8-8z"/>
                 </svg>
              </a>
          </div>
          <a href="../assets/pdf/li.pdf" download class="downloadCV">Download CV</a>

      </div>
  </div>
</template>

<style lang="scss" scoped>
    $mainColor:#FE8696;
    $mainColor:#02377B;
    #about{
        padding: 150px 0 100px;
        display: flex;
        width:100%;
        max-width:1000px;
        justify-content: center;
        margin: 0 auto;
        align-items: center;
        @media screen and (max-width:975px){
            flex-direction: column;
        }
        >.imgBox{
            width:400px;
            height: 500px;
            object-fit: cover;
            margin-right: 50px;
            @media screen and (max-width:1100px){
                width:400px;
                height: 400px;
                margin-right: 0;
            }
             @media screen and (max-width:975px){
                margin-right: 0;
                width:80%;
                max-width: 500px;
                height: auto;
                margin-bottom: 30px;
            }
            >img{
                width:100%;
                height: 500px;
                object-fit: cover;
                 -webkit-filter:grayscale(.3);
                  @media screen and (max-width:975px){
                    width:100%;
                    height: 100%;
                }
            }
        }
        >.content{
            margin-left:50px;
            width:500px;
            letter-spacing: 1px;
            @media screen and (max-width:975px){
                width:80%;
                margin-left:0;
            }
            >.myTitle{
                color:$mainColor;
                font-weight: 700;
                font-size: 17px;
                margin-bottom: 10px;
                display: block;
            }
            >.aboutMe{
                color:#000;
                font-size: 36px;
                font-weight: 900;
                margin-bottom: 20px;
            }
            >.intro{
                color:#888;
                font-size: 15px;
                margin-bottom: 30px;
                >li{
                    margin-bottom: 5px;
                    margin-left: 25px;
                }
            }
            >.basic{
                font-size: 16px;
                font-weight: 600;
                display: flex;
                align-items: center;
                letter-spacing: 1px;
                margin:10px 0;
                @media screen and (max-width:520px){
                    font-size: 19px;
                }
                 @media screen and (max-width:425px){
                    flex-direction: column;
                    align-items: flex-start;
                }
                @media screen and (max-width:333px){
                    font-size: 16px;
                }
                >p.question{
                    width:120px;
                    color:#000;
                    @media screen and (max-width:520px){
                        width:100px;
                        min-width:100px;
                    }
                }
                >p.answer{
                    color:#333;
                    font-weight: 500;
                }
            }
            >.icon{
                display: flex;
                >a{
                    margin: 15px 20px 5px 0;
                    >svg{
                        color:#333;
                        transition: .3s;
                        &:hover{
                            color:#000;
                            transform: scale(1.2);
                            animation: scaleAnim .5s;
                            @keyframes scaleAnim {
                                0%{
                                    transform: scale(1);
                                }
                               30%{
                                   transform: scale(.9);
                               }
                                100%{
                                    transform: scale(1.2);
                                }
                            }
                        }

                    }
                }
            }
            >.downloadCV{
                display: block;
                text-align: center;
                line-height:56px ;
                border:2px $mainColor solid;
                border-radius: 40px;
                font-size: 16px;
                width:180px;
                height: 60px;
                font-weight: 600;
                color:$mainColor;
                transition: .3s;
                margin-top: 30px;
                &:hover{
                    background-color: $mainColor;
                    color:#fff;
                    transition: .3s;
                }
            }
        }
    }
</style>