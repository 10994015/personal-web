<script>
export default {

}
</script>
<template>
  <div id="banner">
      <img src="@/assets/images/about.jpg" alt="">
      <div class="text open">
          <h2>Li-Cheng Yan</h2>
          <p>I come from Taoyuan</p>
          <a href="javascript:;">SEE MORE</a>
      </div>
  </div>
</template>

<style lang="scss" scoped>
    #banner{
        width:100%;
        height: 100vh;
        position: relative;
        >img{
            width:50%;
            height: 100%;
            object-fit: cover;
            border-radius: 100% 100% 100% 100% / 0% 0% 60% 0%;
            display: block;
            -webkit-filter:grayscale(.5);
        }
        >.text{
            position: absolute;
            background-color: transparent;
            top: 50%;
            left:60%;
            transform: translate(-50%,-50%);
            display: flex;
            flex-direction: column;
            align-items: flex-end;
            &.open{
                animation: openText 1s ;
                @keyframes openText {
                    0%{
                        margin-top:60px;
                        opacity: 0;
                    }
                    100%{
                        margin-top:0;opacity: 1;
                        
                    }
                }
            }
            >h2{
                font-size: 70px;
                font-weight: 900;
                font-family: sans-serif;
            }
            >p{
                font-size: 30px;
                color:#777;
                margin:10px 0;
            }
            >a{
                display: block;
                text-align: center;
                line-height:56px ;
                border:2px #FE8696 solid;
                border-radius: 30px;
                font-size: 18px;
                width:180px;
                height: 60px;
                font-weight: 600;
                color:#FE8696;
                transition: .3s;
                margin-top: 30px;
                &:hover{
                    background-color: #FE8696;
                    color:#fff;
                    transition: .3s;
                }

            }
        }
    }
</style>