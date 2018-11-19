<template>
  <div class="hello">
    <div class="header">
      <div class="left-header">
        <a class="logo" href="http://mail.163.com/html/mail_intro/" ></a>
        <a class="slogan" href="http://mail.163.com/html/mail_intro/">中文邮箱第一品牌</a>
      </div>
      <div class="right-header">
        <a href="http://qiye.163.com/" target="_blank">企业邮箱</a>
        <a href="http://qiye.163.com/" target="_blank">VIP邮箱</a>
        <a href="http://qiye.163.com/" target="_blank">国外用户登录</a>
        <a href="http://qiye.163.com/" target="_blank">手机版</a>
        <a href="http://qiye.163.com/" target="_blank">电脑版</a>
        <a href="http://qiye.163.com/" target="_blank">帮助</a>
        <a href="http://qiye.163.com/" target="_blank">常见问题</a>
        <a href="http://qiye.163.com/" target="_blank">私人助理</a>
        <a href="http://qiye.163.com/" target="_blank">登录反馈</a>
      </div>
    </div>
    <div class="content">
      <div class="ad-img"></div>
      <div class="login_box">
        <div class="box">
        <div class="select_login">
          <span class="login"><a :class="{'active':loginActive==true}" @mouseenter="loginSelectedQrCode" @mouseleave="loginSelectedQrCode">二维码登录</a></span>
          <span class="login"><a :class="{'active':loginAccountActive==true}" @mouseenter="loginSelectedAccount" @mouseleave="loginSelectedAccount">邮箱账号登录</a></span>
        </div>
        <div class="login_enter">
          <div class="account">
            <i class="icon_user"></i>
            <input type="text" name="account" placeholder="邮箱账号或手机号码">
            <span>@163.com</span>
          </div>
          <div class="account">
            <i class="icon_lock"></i>
            <input type="text" name="password" placeholder="输入密码">
          </div>
           <div class="unlogin">
            <span class="checkbox" name="unlogin" :class="{'checked':checked==true}" @click="changeChecked"></span>
            <span>十天之内免登陆</span>
            <span class="forget"><a>忘记密码？</a></span>
          </div>
          <div class="button-group">
            <span>登录</span>
            <span>注册</span>
          </div>
        </div>
        <div class="desc"></div>
        <div class="yan_xuan">
          <p>网易自营电商严选30天无忧退货</p><p>网易邮箱提醒您谨防邮件诈骗</p>
        </div>
      </div>
      </div>
    </div>  
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      loginActive: false, // 二维码登录选中
      loginAccountActive: false, //账号登录选中
      checked:false
    }
  },
  methods: {
    loginSelectedQrCode: function(){
      this.loginActive = !this.loginActive; 
    },
    loginSelectedAccount:function(){
      this.loginAccountActive = !this.loginAccountActive; 
    },
    changeChecked:function(){
      this.checked = !this.checked;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.hello{
   .header{
      margin:16px 190px;
      display:flex;
      margin-bottom:16px;
    .left-header{ 
      flex: 0 0 410px;
      width:410px;
      display:flex;
      align-items: center;
      .logo{
        margin-right:10px;
        background-color:red;
        display:inline-block;
        width:136px;
        height:32px;
        background:url("https://mimg.127.net/index/163/scripts/2017/pc//img/163logo@2x.png") 50% no-repeat;
        background-size: 100% 100%;
      }
      .slogan{
        display:inline-block;
        text-decoration:none;
        padding:0 14px;
        font-size:16px;
        color:#777777;
        border-left:1px solid #ccc;
        height:28px;
        line-height:28px;
      }
    }
    .right-header{
      flex:1;
      display:flex;
      align-items: center;
      flex-wrap:nowrap;
      a{
        display:inline-block;
        text-decoration:none;
        font-size:12px;
        margin-right:15px;
        color:#848585;
      }
    }
  }
  .content{
    background-color: #ddd;
    position:relative;
    .ad-img{
      margin-left:190px;
      background-image: url("https://mimg.127.net/m/lc/img/LoginBackgroundPic/1730/5/promPic.jpg");
      background-repeat: no-repeat;
      height: 600px;
      width:100%;
    }
    .login_box{
      position:absolute;
      width:450px;
      height:490px;
      top:28px;
      right:180px;
      border:1px solid #ccccca;
      border-radius: 4px;
      background-color: #fff;
      box-shadow:0px 0px  2px 2px #c4c5c0;
      overflow: hidden;
      .box{
        position:relative;
      }
      .select_login{
        height:45px;
        line-height: 45px;
        background-color:#fefefe;
        display:flex;
        text-align: center;
        .login{
          flex:1;
          color:#626262;
          a{
            &.active{
              display:inline-block;
              color:#31a1e9;
              padding:0 2px;
              border-bottom: 2px solid #3182d9;
            }
          }
        }
      }
      .login_enter{
        /*height:46px;
        width:330px;
        border:1px solid #c5cddb;*/
        .account{
          &:nth-child(1){
            margin-top:40px;
          }  
          margin-left:60px;
          position:relative;
          margin-bottom:18px;
          .icon_user{
            position:absolute;
            display:inline-block;
            width:22px;
            height:24px;
            background: url("https://urswebzj.nosdn.127.net/webzj_cdn101/sprite_61fbe151ab715649c6b7c4ec39156201.png") -9999px -9999px no-repeat;
            background-position: -251px -86px;
            margin-top:10px;
            margin-left:8px;
          }
          input{
            height:46px;
            width:330px;
            box-sizing: border-box;
            padding-left:38px;
            padding-right:86px;
            color: #333;
            font-size: 16px;
            font-weight: bold;
          }
          input::-webkit-input-placeholder{
              color: #dbdbdb;
              font-size:12px;
              font-weight: 400;
              letter-spacing: 0.6px;
          }
          span{
            display:inline-block;
            position:absolute;
            font-size:16px;
            right:68px;
            top:13px;
            color:#616161;
          }
          .icon_lock{
            position:absolute;
            display:inline-block;
            width:22px;
            height:24px;
            background: url("https://urswebzj.nosdn.127.net/webzj_cdn101/sprite_61fbe151ab715649c6b7c4ec39156201.png") -9999px -9999px no-repeat;
            background-position: -291px -86px;;
            margin-top:10px;
            margin-left:8px;
          }
        }
        .unlogin{
          margin-left:60px;
          margin-right:60px;
          position:relative;
          .checkbox{
            display:inline-block;
            width:14px;
            height:14px;
            border:1px solid #aaa;
            color:#999;
            background: url("https://urswebzj.nosdn.127.net/webzj_cdn101/sprite_61fbe151ab715649c6b7c4ec39156201.png") -9999px -9999px ;
            margin-right:8px;
            &.checked{
              background-position: -330px -92px;
            }
          }
           span:nth-of-type(2){
            display:inline-block;
            height:16px;
            line-height: 17px;
            font-size:12px;
            color:#999;
          /*  margin-top:2px;*/
            vertical-align: top;
          }
          .forget{
            display:inline-block;
            color:#6a82e0;
            font-size:12px;
            float:right;
          }
        }
        .button-group{
          margin-top:26px;
          margin:26px 60px 0px 60px;
          text-align: center;
          span{
            display: inline-block;
            width:160px;
            height:46px; 
            line-height: 48px;           
            border-radius: 4px;
            font-weight:bold;
          }
          span:nth-of-type(1){
            border:1px solid transparent;
            background-color: #3182d9;
            color:#fff;
            font-size:16px;
            letter-spacing: 10px;
            text-align: center;
          }
          span:nth-of-type(2){
            border:1px solid #abccef;
            background-color: #eaf2fb;
            color:#3182d9;
            font-size:16px;
            letter-spacing: 10px;
            text-align: center;
          }
        }
      }
      .desc{
        margin-top:40px;
        margin-left:60px;
        width:256px;
        height:35px;
        background: url("https://mimg.127.net/index/163/scripts/2017/pc//img/mailvip_logo_1.png") 50% no-repeat;
        background-size: 100% 100%;
      }
      .yan_xuan{
        margin-top:32px;
        bottom:0px;
        width:100%;
        height:74px;
        left:0;
        background-color: #fafafa;
        p{
          color:#999;
          margin-left:60px;
          font-size:12px;
          height:12px;
          line-height: 12px;
          &:nth-of-type(1){
            padding-top:18px;
          };
        }
      }
    }
  }
}
</style>
