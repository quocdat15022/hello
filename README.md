<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Chẵn Lẻ Tài Xỉu</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        background: #f4f4f4;
        text-align: center;
        margin: 0;
        padding: 0;
      }
      .container {
        max-width: 600px;
        margin: 50px auto;
        background: #ffffff;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
      }
      h1 {
        color: #333;
      }
      .choices {
        display: flex;
        justify-content: space-around;
        margin-top: 20px;
      }
      .choice {
        padding: 15px 20px;
        background: #007bff;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 16px;
      }
      .choice:hover {
        background: #0056b3;
      }
      .result {
        margin-top: 20px;
        font-size: 18px;
        color: #28a745;
      }
      .dice {
        margin-top: 20px;
        font-size: 24px;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <h1>Chẵn Lẻ Tài Xỉu</h1>
      <p>Chọn Chẵn, Lẻ, Tài, hoặc Xỉu để bắt đầu trò chơi!</p>
      <div class="choices">
        <button class="choice" onclick="playGame('chan')">Chẵn</button>
        <button class="choice" onclick="playGame('le')">Lẻ</button>
        <button class="choice" onclick="playGame('tai')">Tài</button>
        <button class="choice" onclick="playGame('xiu')">Xỉu</button>
      </div>
      <div class="result" id="result"></div>
      <div class="dice" id="dice"></div>
    </div>

    <script>
      function playGame(choice) {
        // Mô phỏng xúc xắc (3 xúc xắc)
        const dice1 = Math.floor(Math.random() * 6) + 1;
        const dice2 = Math.floor(Math.random() * 6) + 1;
        const dice3 = Math.floor(Math.random() * 6) + 1;
        const total = dice1 + dice2 + dice3;

        // Hiển thị kết quả xúc xắc
        document.getElementById(
          "dice"
        ).innerText = `Xúc xắc: ${dice1}, ${dice2}, ${dice3} (Tổng: ${total})`;

        // Xác định chẵn/lẻ
        const chanLe = total % 2 === 0 ? "chan" : "le";
        // Xác định tài/xỉu
        const taiXiu = total >= 11 ? "tai" : "xiu";

        // Kiểm tra kết quả
        if (choice === chanLe || choice === taiXiu) {
          document.getElementById("result").innerText =
            "Chúc mừng! Bạn đã thắng!";
        } else {
          document.getElementById("result").innerText =
            "Rất tiếc! Bạn đã thua!";
        }
      }
    </script>
  </body>
</html>
