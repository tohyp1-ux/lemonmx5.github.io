<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>MX-5 Lemonade Goal</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f7f7f7;
      text-align: center;
      padding: 20px;
    }
    h1 {
      color: #d32f2f;
    }
    .container {
      max-width: 800px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }
    .input-group {
      margin: 15px 0;
    }
    input {
      padding: 10px;
      width: 100px;
      font-size: 16px;
      margin-left: 10px;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      background: #388e3c;
      color: white;
      border: none;
      border-radius: 6px;
      cursor: pointer;
    }
    button:hover {
      background: #2e7d32;
    }
    .result {
      margin-top: 20px;
      font-size: 18px;
      font-weight: bold;
    }
    .images {
      margin-top: 30px;
      display: flex;
      justify-content: center;
      gap: 15px;
    }
    .images img {
      width: 250px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>MX-5 Lemonade Goal Tracker</h1>
    <p>目标金额: RM150,000</p>
    <p>Lemonade 一杯赚 RM2 | Fresh Juice 一杯赚 RM2.5</p>

    <div class="input-group">
      <label>卖出的 Lemonade (杯): </label>
      <input type="number" id="lemonade" value="0">
    </div>

    <div class="input-group">
      <label>卖出的 Fresh Juice (杯): </label>
      <input type="number" id="juice" value="0">
    </div>

    <button onclick="calculate()">计算剩余目标</button>

    <div class="result" id="result"></div>

    <div class="images">
      <img src="https://upload.wikimedia.org/wikipedia/commons/4/46/Mazda_MX-5_RF_IMG_2683.jpg" alt="MX-5 1">
      <img src="https://upload.wikimedia.org/wikipedia/commons/f/f2/2018_Mazda_MX-5_%28ND2%29_RF_hardtop_convertible_%282018-10-12%29_01.jpg" alt="MX-5 2">
      <img src="https://upload.wikimedia.org/wikipedia/commons/7/70/Mazda_MX-5_%28ND%29_%E2%80%93_Frontansicht%2C_1._August_2015%2C_D%C3%BCsseldorf.jpg" alt="MX-5 3">
    </div>
  </div>

  <script>
    function calculate() {
      const lemonade = parseInt(document.getElementById('lemonade').value) || 0;
      const juice = parseInt(document.getElementById('juice').value) || 0;

      const earnings = lemonade * 2 + juice * 2.5;
      const goal = 150000;
      const remaining = goal - earnings;

      let message;
      if (remaining > 0) {
        message = `你已经赚了 RM${earnings.toFixed(2)}，还差 RM${remaining.toFixed(2)} 才能买 MX-5 🚗`;
      } else {
        message = `恭喜！你已经赚够 RM${earnings.toFixed(2)} 买 MX-5 🚗🎉`;
      }

      document.getElementById('result').innerText = message;
    }
  </script>
</body>
</html>
