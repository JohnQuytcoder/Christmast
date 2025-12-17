<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Nhập mật khẩu</title>
<style>
    body {
        background: linear-gradient(135deg, #fbc2eb, #a6c1ee);
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        font-family: Arial;
    }

    .box {
        background: white;
        padding: 20px;
        border-radius: 15px;
        width: 300px;
        text-align: center;
        box-shadow: 0 10px 30px rgba(0,0,0,.2);
    }

    h2 {
        color: hotpink;
        margin-bottom: 10px;
    }

    input {
        width: 100%;
        padding: 10px;
        font-size: 18px;
        text-align: center;
        margin-bottom: 15px;
        border-radius: 8px;
        border: 1px solid #ccc;
    }

    .keypad {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 10px;
    }

    button {
        padding: 15px;
        font-size: 18px;
        border-radius: 10px;
        border: none;
        background: #ffb6c1;
        cursor: pointer;
    }

    button:hover {
        background: hotpink;
        color: white;
    }

    .clear {
        background: #ccc;
    }

    .ok {
        background: #7bed9f;
    }
</style>
</head>
<body>

<div class="box">
    <h2>🔒 Hãy nhập mật khẩu 💕</h2>
    <input type="password" id="pwd" readonly placeholder="****">

    <div class="keypad">
        <button onclick="press(1)">1</button>
        <button onclick="press(2)">2</button>
        <button onclick="press(3)">3</button>
        <button onclick="press(4)">4</button>
        <button onclick="press(5)">5</button>
        <button onclick="press(6)">6</button>
        <button onclick="press(7)">7</button>
        <button onclick="press(8)">8</button>
        <button onclick="press(9)">9</button>
        <button class="clear" onclick="clearPwd()">X</button>
        <button onclick="press(0)">0</button>
        <button class="ok" onclick="checkPwd()">OK</button>
    </div>
</div>

<script>
    let password = "";
    const correct = "1234"; // đổi mật khẩu ở đây

    function press(num) {
        if (password.length < 6) {
            password += num;
            document.getElementById("pwd").value = password;
        }
    }

    function clearPwd() {
        password = "";
        document.getElementById("pwd").value = "";
    }

    function checkPwd() {
        if (password === correct) {
            alert("🎉 Đúng mật khẩu rồi nè!");
        } else {
            alert("❌ Sai mật khẩu nha!");
            clearPwd();
        }
    }
</script>

</body>
</html>
