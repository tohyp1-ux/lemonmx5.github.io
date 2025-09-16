<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MX-5 Lemon & Juice Sale</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 20px;
        }
        img {
            max-width: 80%;
            height: auto;
            margin: 20px 0;
            border: 2px solid #ccc;
            border-radius: 10px;
        }
        .progress-container {
            width: 80%;
            background-color: #eee;
            margin: 20px auto;
            border-radius: 20px;
            overflow: hidden;
        }
        .progress-bar {
            height: 30px;
            width: 0%;
            background-color: #4caf50;
            line-height: 30px;
            color: white;
            font-weight: bold;
        }
        input {
            width: 60px;
            text-align: center;
        }
    </style>
</head>
<body>
    <h1>MX-5 Lemon & Juice Sale</h1>
    
    <p>目标：购买 MX-5（假设价格 3000 SGD）</p>
    
    <div>
        <label>卖出柠檬水数量（杯）: <input type="number" id="lemon" value="0"></label><br><br>
        <label>卖出果蔬汁数量（杯）: <input type="number" id="juice" value="0"></label><br><br>
        <button onclick="updateProgress()">更新进度</button>
    </div>
    
    <div class="progress-container">
        <div class="progress-bar" id="progressBar">0%</div>
    </div>
    
    <p id="moneyInfo">已赚: 0 SGD / 3000 SGD</p>
    
    <h2>看看我们的 MX-5</h2>
    <img src="50-50-01-ext.jpg" alt="MX-5 Exterior">
    <img src="50-50-01-holistic.jpg" alt="MX-5 Holistic View">
    <img src="mx5-manual.png" alt="MX-5 Manual">

    <script>
        const priceMX5 = 3000; // 目标金额
        const priceLemon = 3; // 假设每杯柠檬水 3 SGD
        const priceJuice = 5; // 每杯果蔬汁 5 SGD

        function updateProgress() {
            const lemonCount = parseInt(document.getElementById('lemon').value) || 0;
            const juiceCount = parseInt(document.getElementById('juice').value) || 0;

            const totalMoney = lemonCount * priceLemon + juiceCount * priceJuice;
            let percent = Math.min((totalMoney / priceMX5) * 100, 100);
            
            document.getElementById('progressBar').style.width = percent + '%';
            document.getElementById('progressBar').textContent = Math.floor(percent) + '%';
            document.getElementById('moneyInfo').textContent = `已赚: ${totalMoney} SGD / ${priceMX5} SGD`;
        }
    </script>
</body>
</html>

