
成績預估排名系統

<html lang="zh-Hant">
<head>
  <meta charset="UTF-8">
  <title>會考預估排名系統</title>
  <style>
    body {
      background-color: #f8f4ef;
      font-family: "Helvetica Neue", Arial, sans-serif;
      color: #3e2f28;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 20px;
    }
    select, button {
      margin: 10px;
      padding: 12px;
      font-size: 16px;
      border-radius: 8px;
      border: 1px solid #d6c8ba;
      background-color: #fff;
      width: 250px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.05);
    }
    button {
      background-color: #d8b4a0;
      color: #fff;
      font-weight: bold;
      transition: background-color 0.3s;
    }
    button:hover {
      background-color: #b59382;
    }
    .card {
      background-color: #ffffff;
      padding: 30px;
      margin-top: 30px;
      border-radius: 12px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
      width: 90%;
      max-width: 600px;
      text-align: center;
    }
    .info {
      margin: 10px 0;
      padding: 12px;
      border-radius: 8px;
      background-color: #f1e7de;
      font-size: 20px;
      color: #5c4a42;
    }
    .highlight {
      font-size: 24px;
      font-weight: bold;
      color: #7a5c51;
      background-color: #f4eae3;
      padding: 12px;
      border-radius: 8px;
      display: inline-block;
      margin: 10px 0;
    }
    .description {
      margin: 15px 0;
      font-size: 16px;
      color: #5a5147;
      text-align: center;
      max-width: 600px;
    }
    .footer {
      margin-top: 30px;
      font-size: 14px;
      color: #666;
      padding: 10px;
      border-top: 1px solid #ccc;
      width: 100%;
      text-align: center;
    }
    h1 {
      font-weight: 600;
      font-size: 28px;
      color: #4d3b33;
      margin-bottom: 30px;
    }
    .big-title {
      font-size: 32px;
      font-weight: bold;
      color: #3e2f28;
      margin-bottom: 20px;
    }
  </style>
</head>
<body>
  <div class="big-title">114國中教育會考</div>

  <h1>會考預估排名系統</h1>

  <select id="region">
    <option value="">請選擇考區</option>
    <option value="21311">臺北考區</option>
    <option value="29825">新北考區</option>
    <option value="3561">宜蘭考區</option>
    <option value="2392">基隆考區</option>
    <option value="18474">桃園考區</option>
    <option value="14022">竹苗考區</option>
    <option value="29181">中投考區</option>
    <option value="9041">彰化考區</option>
    <option value="4953">雲林考區</option>
    <option value="5169">嘉義考區</option>
    <option value="13373">臺南考區</option>
    <option value="5102">屏東考區</option>
    <option value="18796">高雄考區</option>
    <option value="2400">花蓮考區</option>
    <option value="1472">臺東考區</option>
    <option value="524">澎湖考區</option>
    <option value="589">金門考區</option>
    <option value="80">馬祖考區</option>
  </select>

  <div class="description">
    會考成績公布了～看看自己的考區排名，幫助你更快找到適合的學校！<br>
    只要輸入自己的考區和成績就可以囉！
  </div>

  <div>
    <select id="chinese">
      <option value="">國文</option>
      <option value="A">A++</option>
      <option value="A">A+</option>
      <option value="A">A</option>
      <option value="B">B++</option>
      <option value="B">B+</option>
      <option value="B">B</option>
      <option value="C">C++</option>
      <option value="C">C+</option>
      <option value="C">C</option>
    </select>
    <select id="math">
      <option value="">數學</option>
      <option value="A">A++</option>
      <option value="A">A+</option>
      <option value="A">A</option>
      <option value="B">B++</option>
      <option value="B">B+</option>
      <option value="B">B</option>
      <option value="C">C++</option>
      <option value="C">C+</option>
      <option value="C">C</option>
    </select>
    <select id="english">
      <option value="">英文</option>
      <option value="A">A++</option>
      <option value="A">A+</option>
      <option value="A">A</option>
      <option value="B">B++</option>
      <option value="B">B+</option>
      <option value="B">B</option>
      <option value="C">C++</option>
      <option value="C">C+</option>
      <option value="C">C</option>
    </select>
    <select id="science">
      <option value="">理化</option>
      <option value="A">A++</option>
      <option value="A">A+</option>
      <option value="A">A</option>
      <option value="B">B++</option>
      <option value="B">B+</option>
      <option value="B">B</option>
      <option value="C">C++</option>
      <option value="C">C+</option>
      <option value="C">C</option>
    </select>
    <select id="social">
      <option value="">社會</option>
      <option value="A">A++</option>
      <option value="A">A+</option>
      <option value="A">A</option>
      <option value="B">B++</option>
      <option value="B">B+</option>
      <option value="B">B</option>
      <option value="C">C++</option>
      <option value="C">C+</option>
      <option value="C">C</option>
    </select>
  </div>

  <button onclick="calculateRank()">計算排名</button>

  <div class="card" id="result" style="display:none;">
    <div id="grade" class="info"></div>
    <div id="regionName" class="info"></div>
    <div id="ranking" class="highlight"></div>
    <div id="percent" class="highlight"></div>
  </div>

  <div class="footer">排名依照大考中心公布之各級人數百分比統計表預估，僅供參考</div>

  <script>
    const scoreData = {
      "5A0B0C": 9.29,
      "4A1B0C": 5.47,
      "4A0B1C": 0.02,
      "3A2B0C": 5.45,
      "3A1B1C": 0.05,
      "3A0B2C": 0.00,
      "2A3B0C": 7.02,
      "2A2B1C": 0.18,
      "2A1B2C": 0.01,
      "2A0B3C": 0.00,
      "1A4B0C": 10.99,
      "1A3B1C": 1.06,
      "1A2B2C": 0.15,
      "1A1B3C": 0.03,
      "1A0B4C": 0.02,
      "0A5B0C": 22.75,
      "0A4B1C": 11.70,
      "0A3B2C": 7.99,
      "0A2B3C": 6.10,
      "0A1B4C": 5.10,
      "0A0B5C": 6.62
    };

    const regionNames = {
      "21311": "臺北考區",
      "29825": "新北考區",
      "3561": "宜蘭考區",
      "2392": "基隆考區",
      "18474": "桃園考區",
      "14022": "竹苗考區",
      "29181": "中投考區",
      "9041": "彰化考區",
      "4953": "雲林考區",
      "5169": "嘉義考區",
      "13373": "臺南考區",
      "5102": "屏東考區",
      "18796": "高雄考區",
      "2400": "花蓮考區",
      "1472": "臺東考區",
      "524": "澎湖考區",
      "589": "金門考區",
      "80": "馬祖考區"
    };

    function calculateRank() {
      const region = document.getElementById("region").value;
      const scores = [
        document.getElementById("chinese").value,
        document.getElementById("math").value,
        document.getElementById("english").value,
        document.getElementById("science").value,
        document.getElementById("social").value
      ];

      if (!region || scores.includes("")) {
        alert("請選擇考區並填寫所有科目成績！");
        return;
      }

      const A = scores.filter(s => s === 'A').length;
      const B = scores.filter(s => s === 'B').length;
      const C = scores.filter(s => s === 'C').length;
      const gradeCombo = `${A}A${B}B${C}C`;

      const percent = scoreData[gradeCombo];
      if (percent === undefined) {
        document.getElementById("grade").innerText = `成績類別：${gradeCombo}`;
        document.getElementById("regionName").innerText = `考區：${regionNames[region]}`;
        document.getElementById("ranking").innerText = `查無資料，可能無人考到此組合`;
        document.getElementById("percent").innerText = "";
        document.getElementById("result").style.display = "block";
        return;
      }

      const totalStudents = parseInt(region);
      const estimatedStart = 1;
      const estimatedEnd = Math.floor(totalStudents * (percent / 100));

      document.getElementById("grade").innerText = `成績類別：${gradeCombo}`;
      document.getElementById("regionName").innerText = `考區：${regionNames[region]}`;
      document.getElementById("ranking").innerText = `預估排名範圍：第 ${estimatedStart} 名 ～ 第 ${estimatedEnd} 名`;
      document.getElementById("percent").innerText = `預估百分比範圍：0% ～ ${percent.toFixed(2)}%`;
      document.getElementById("result").style.display = "block";
    }
  </script>
</body>
</html>
