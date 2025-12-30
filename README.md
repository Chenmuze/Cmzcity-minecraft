<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CMZCity Plan A</title>
    <style>
        * {margin: 0;padding: 0;box-sizing: border-box;}
        body {
            background: #1a1a1a;
            font-family: "Microsoft Yahei", sans-serif;
            color: #fff;
            padding: 20px;
            background-image: url("https://images.unsplash.com/photo-1628625885433?w=100&h=100&auto=format");
            background-attachment: fixed;
            background-size: 128px;
            background-repeat: repeat;
            background-blend-mode: overlay;
        }
        .login-mask {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.9);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 999;
        }
        .login-box {
            background: rgba(24,24,24,0.95);
            border: 2px solid #55ff55;
            border-radius: 12px;
            padding: 40px 30px;
            width: 90%;
            max-width: 400px;
            text-align: center;
        }
        .login-box h2 {
            color: #55ff55;
            margin-bottom: 25px;
            text-shadow: 0 0 8px #55ff55;
        }
        .login-input {
            width: 100%;
            padding: 12px 15px;
            border: 1px dashed #4CAF50;
            background: rgba(0,0,0,0.5);
            color: #fff;
            border-radius: 8px;
            font-size: 1rem;
            margin-bottom: 15px;
            outline: none;
        }
        .login-input:focus {
            border: 1px solid #55ff55;
            box-shadow: 0 0 10px rgba(85,255,85,0.3);
        }
        .login-btn {
            padding: 12px 30px;
            background: rgba(34,139,34,0.8);
            border: 2px solid #55ff55;
            color: #fff;
            border-radius: 8px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s;
            margin-top: 10px;
        }
        .login-btn:hover {
            background: rgba(34,139,34,1);
            box-shadow: 0 0 15px #55ff55;
        }
        .header {
            text-align: center;
            padding: 30px 0;
            background: rgba(34,139,34,0.8);
            border-radius: 12px;
            margin-bottom: 30px;
            border: 2px solid #55ff55;
        }
        .header h1 {
            font-size: 2.5rem;
            color: #f0f8ff;
            text-shadow: 0 0 10px #55ff55;
        }
        .header p {
            margin-top: 10px;
            color: #d0ffd0;
            font-size: 1.1rem;
        }
        .member-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px,1fr));
            gap: 25px;
        }
        .member-card {
            background: rgba(24,24,24,0.9);
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            border: 1px dashed #4CAF50;
            transition: all 0.3s;
        }
        .member-card:hover {
            border: 1px solid #55ff55;
            box-shadow: 0 0 15px rgba(85,255,85,0.5);
        }
        .creator-card {
            border: 2px solid #55ff55;
            background: rgba(20,40,20,0.95);
        }
        .creator-card:hover {
            box-shadow: 0 0 20px #55ff55;
        }
        .member-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            margin: 0 auto 15px;
            border: 3px dashed #4CAF50;
            background: rgba(0,0,0,0.5);
            display:flex;align-items:center;justify-content:center;
            color:#999;
        }
        .creator-avatar {
            border: 3px solid #55ff55;
            color: #55ff55;
        }
        .member-name {
            font-size:1.5rem; color:#999; margin-bottom:10px;
        }
        .creator-name {
            color: #55ff55;
            text-shadow: 0 0 8px #55ff55;
        }
        .member-info p {
            color:#666; line-height:1.6; margin:5px 0;
        }
        .creator-info p {
            color: #d0ffd0;
        }
        .footer {
            margin-top: 20px;
            padding: 20px;
            background: rgba(34,139,34,0.8);
            border-radius: 12px;
            border: 2px solid #55ff55;
        }
        .content {display: none;}
    </style>
</head>
<body>
    <!-- 用户名+邀请码登录弹窗 -->
    <div class="login-mask" id="loginMask">
        <div class="login-box">
            <h2>CMZCity 邀请登录</h2>
            <input type="text" class="login-input" id="userName" placeholder="请填写用户名">
            <input type="text" class="login-input" id="inviteCode" placeholder="请输入邀请码">
            <button class="login-btn" onclick="checkInvite()">验证登录</button>
        </div>
    </div>

    <!-- 完全还原之前绿框样式，无多余文字 -->
    <div class="content" id="mainContent">
        <div class="header">
            <h1>CMZCity Plan A</h1>
            <p>创建者：Chenmuze_</p>
        </div>
        <div class="member-container">
            <div class="member-card creator-card">
                <div class="member-avatar creator-avatar">创建者</div>
                <h3 class="member-name creator-name">Chenmuze_</h3>
                <div class="member-info creator-info">
                    <p>加入：创始</p>
                </div>
            </div>
            <div class="member-card">
                <div class="member-avatar">暂无</div>
                <h3 class="member-name">成员ID</h3>
                <div class="member-info">
                    <p>加入：待填写</p>
                </div>
            </div>
            <div class="member-card">
                 <div class="member-avatar">暂无</div> 
                 <h3 class="member-name">成员ID</h3> 
     <div class="member-info"> 
                     <p>加入：待填写</p> 
     </div> 
     </div> 
     <div class="member-card"> 
                 <div class="member-avatar">暂无</div> 
                 <h3 class="member-name">成员ID</h3> 
     <div class="member-info"> 
                     <p>加入：待填写</p> 
     </div> 
     </div> 
     <div class="member-card"> 
                 <div class="member-avatar">暂无</div> 
                 <h3 class="member-name">成员ID</h3> 
     <div class="member-info"> 
                     <p>加入：待填写</p> 
     </div> 
     </div> 
     <div class="member-card"> 
                 <div class="member-avatar">暂无</div> 
                 <h3 class="member-name">成员ID</h3> 
     <div class="member-info"> 
                     <p>加入：待填写</p> 
     </div> 
     </div> 
     </div> 
     <div class="footer"></div> 
    </div>

    <脚本>
         // 双项必填，填就过，无多余提示，跳转稳 
     函数 checkInvite () { 
     Let name = document.getElementById ("userName")value.trim (); 
     let code = document.getElementById ("inviteCode")value.trim (); 
     if(name === "" || code === ""){ 
                 alert("用户名和邀请码都不能为空～"); 
     返回； 
             } 
     document.getElementById ("loginMask")style.display = "none"; 
     document.getElementById ("mainContent")style.display = "block"; 
         } 
         // 回车登录 
     document.addEventListener ('keydown',e=>{ 
     if (e.key === 'Enter') checkInvite (); 
         }); 
    </script>
身体
</html>html>
