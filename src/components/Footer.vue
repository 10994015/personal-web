<script>
export default {

}
</script>
<template>
  <footer id="footer">
      <h3>Copyright @2022 <a href="./">LiChengYan</a> All Rights Reserved.</h3>
  </footer>
</template>
<style lang="scss" scoped>
    footer#footer{
        width:100%;
        height: 100px;
        background-color: #01163b;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 20px 15px;
        >h3{
            color:#ddd;
            font-size: 16px;
            font-weight: 500;
            letter-spacing: 1px;
            text-align: center;
            >a{
                color:#fff;
                font-weight: 600;
            }
        }
    }
</style>