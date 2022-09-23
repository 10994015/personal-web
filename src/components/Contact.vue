<script>
import axios from 'axios'
import {ref, reactive,} from "vue"
import smtpjs from "@/assets/js/smtp.js"
export default {
  
    setup(){
        // console.log(smtpjs);
        const title = ref(null);
        const name = ref(null);
        const email = ref(null);
        const content = ref(null);
        const data = reactive({
            title:"",
            name:"",
            email:"",
            content:""
        })
        let proxy = 'https://cors-anywhere.herokuapp.com/';
        const sendMail  = ()=> {
            smtpjs.send({
                SecureToken: 'c4a9e729-3af3-48ac-8799-b7f38b7853a7',
                To: 'a0938599191@gmail.com',
                From: 'a0938599191@gmail.com',
                Subject: '主旨',
                Body: '內容'
            }).then(
                message => alert(message)
            )
        }
        
        const handSubmit = ()=>{
            let params = new FormData();
            params.append('title',title.value )
            params.append('name',name.value )
            params.append('email', email.value)
            params.append('content', content.value)
            // console.log('params=>', params);
            
            // axios.post(proxy + 'https://jiousaio.com/sendMail/sendMail.php',params).then(res=>{
            //     console.log(res);
            // })
            // sendMail ()
        }
       
       
        return {data, handSubmit, title,name,email,content};
    },
     
}

</script>
<template>
  <div id="contact">
        <span class="myTitle">CONTACT ME</span>
        <div class="contactForm">
            <input type="text" placeholder="主旨" v-model="data.title" ref="title">
            <input type="text" placeholder="姓名" v-model="data.name" ref="name">
            <input type="text" placeholder="E-mail" v-model="data.email" ref="email">
            <textarea name="" id="" cols="30" rows="10" v-model="data.content" ref="content" placeholder="內容..."></textarea>
            <button @click="handSubmit">送出</button>
        </div>
  </div>
</template>
<style lang="scss" scoped>
$mainColor:#02377B;
    #contact{
        width:100%;
        margin:0 auto;
        padding: 100px 0;
        background-color: #f1f1f1;
         >.myTitle{
            color:$mainColor;
            font-weight: 700;
            font-size: 24px;
            margin-bottom: 30px;
            display: block;
            text-align: center;
            background: transparent;
        }
        >.contactForm{
            width:800px;
            padding: 40px 0;
            background-color: #fff;
            margin:0 auto;
            box-shadow: 0px 10px 20px #ccc;
            display: flex;
            flex-direction: column;
            align-items: center;
            @media screen and (max-width:800px){
                width:90%;
            }
            >input{
                width:80%;
                background-color: #f0f0f0;
                outline: none;
                border:none;
                height: 40px;
                margin:10px 0;
                padding: 0 15px;
                font-size: 14px;
                transition: .3s;
                &:focus{
                    border:2px $mainColor solid;
                }
            }
            textarea{
                width:80%;
                background-color: #f0f0f0;
                outline: none;
                border:none;
                height: 200px;
                resize: none;
                margin:10px 0;
                padding: 15px;
                font-size: 14px;
                transition: .3s;
                 &:focus{
                    border:2px $mainColor solid;
                }
            }
            >button{
                widtH:80%;
                height: 45px;
                border:none;
                outline: none;
                background-color: $mainColor;
                color:#fff;
                font-weight: 600;
                cursor: pointer;
                font-size: 16px;
                transition: .5s;
                border:2px $mainColor solid;
                margin:15px 0;
                &:hover{
                    background-color: transparent;
                    color:$mainColor;
                }
            }
        }
    }
</style>