<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Calculation</title>
    <style>
      body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        font-family: Arial, sans-serif;
        font-size: 18px;
        margin: 0;
      }
      #container {
        text-align: center;
        width: 300px;
      }
      label {
        display: block;
        margin: 10px 0;
      }
      input,
      button,
      textarea {
        display: block;
        width: 100%;
        margin: 10px 0;
        border-radius: 8px;
        border: 1px solid gray;
        box-sizing: border-box;
      }
      input::placeholder {
        color: gray;
        font-size: 16px;
      }
      input {
        height: 40px; /* Adjust this value to change the height */
      }
      button {
        padding: 10px;
        font-size: 18px;
        cursor: pointer;
        background-color: black;
        color: white;
        border: none;
      }
      textarea {
        resize: none;
      }
    </style>
  </head>
  <body>
    <div id="container">
      <label for="degreeInput">導線絕緣溫度:</label>
      <input
        type="text"
        id="degreeInput"
        placeholder="請輸入導線絕緣溫度 (60, 75, 90)"
      />

      <label for="wiresInput">導線數:</label>
      <input type="text" id="wiresInput" placeholder="請輸入導線數為多少" />

      <label for="amphereInput">安培容量:</label>
      <input type="text" id="amphereInput" placeholder="請輸入安培容量" />

      <button id="calculateBtn">Calculate</button>

      <textarea id="result" rows="5" readonly></textarea>
    </div>

    <script>
      document
        .getElementById("calculateBtn")
        .addEventListener("click", function () {
          const degree = document.getElementById("degreeInput").value;
          const numberOfWires = parseInt(
            document.getElementById("wiresInput").value
          );
          const amphereCapacity = parseInt(
            document.getElementById("amphereInput").value
          );
          const resultText = document.getElementById("result");

          function showResult(degree, squareMeters) {
            resultText.value = `導線絕緣溫度 ${degree}℃\n絞線面積為: ${squareMeters}mm²`;
          }

          if (!degree || isNaN(numberOfWires) || isNaN(amphereCapacity)) {
            resultText.value = "輸入錯誤數值";
            return;
          }

          if (degree === "60") {
            if (numberOfWires >= 1 && numberOfWires <= 3) {
              if (amphereCapacity <= 19) {
                showResult(60, 3.5);
              } else if (amphereCapacity <= 25) {
                showResult(60, 5.5);
              } else if (amphereCapacity <= 33) {
                showResult(60, 8);
              } else if (amphereCapacity <= 50) {
                showResult(60, 14);
              } else if (amphereCapacity <= 60) {
                showResult(60, 22);
              } else if (amphereCapacity <= 75) {
                showResult(60, 30);
              } else if (amphereCapacity <= 85) {
                showResult(60, 38);
              } else if (amphereCapacity <= 100) {
                showResult(60, 50);
              } else if (amphereCapacity <= 115) {
                showResult(60, 60);
              } else if (amphereCapacity <= 140) {
                showResult(60, 80);
              } else if (amphereCapacity <= 160) {
                showResult(60, 100);
              } else if (amphereCapacity <= 185) {
                showResult(60, 125);
              } else if (amphereCapacity <= 215) {
                showResult(60, 150);
              } else if (amphereCapacity <= 251) {
                showResult(60, 200);
              } else if (amphereCapacity <= 291) {
                showResult(60, 250);
              } else if (amphereCapacity <= 329) {
                showResult(60, 325);
              } else {
                resultText.value = "Error 1";
              }
            } else if (numberOfWires == 4) {
              if (amphereCapacity == 16) {
                showResult(60, 3.5);
              } else if (amphereCapacity <= 23) {
                showResult(60, 5.5);
              } else if (amphereCapacity <= 30) {
                showResult(60, 8);
              } else if (amphereCapacity <= 40) {
                showResult(60, 14);
              } else if (amphereCapacity <= 55) {
                showResult(60, 22);
              } else if (amphereCapacity <= 65) {
                showResult(60, 30);
              } else if (amphereCapacity <= 75) {
                showResult(60, 38);
              } else if (amphereCapacity <= 90) {
                showResult(60, 50);
              } else if (amphereCapacity <= 105) {
                showResult(60, 60);
              } else if (amphereCapacity <= 125) {
                showResult(60, 80);
              } else if (amphereCapacity <= 150) {
                showResult(60, 100);
              } else if (amphereCapacity <= 165) {
                showResult(60, 125);
              } else if (amphereCapacity <= 190) {
                showResult(60, 150);
              } else if (amphereCapacity <= 225) {
                showResult(60, 200);
              } else {
                resultText.value = "Error 2";
              }
            } else if (numberOfWires >= 5 && numberOfWires <= 6) {
              if (amphereCapacity <= 14) {
                showResult(60, 3.5);
              } else if (amphereCapacity <= 20) {
                showResult(60, 5.5);
              } else if (amphereCapacity <= 25) {
                showResult(60, 8);
              } else if (amphereCapacity <= 35) {
                showResult(60, 14);
              } else if (amphereCapacity <= 50) {
                showResult(60, 22);
              } else if (amphereCapacity <= 55) {
                showResult(60, 30);
              } else if (amphereCapacity <= 65) {
                showResult(60, 38);
              } else if (amphereCapacity <= 80) {
                showResult(60, 50);
              } else if (amphereCapacity <= 90) {
                showResult(60, 60);
              } else if (amphereCapacity <= 105) {
                showResult(60, 80);
              } else if (amphereCapacity <= 125) {
                showResult(60, 100);
              } else if (amphereCapacity <= 140) {
                showResult(60, 100);
              } else {
                resultText.value = "Error 3";
              }
            } else if (numberOfWires >= 7 && numberOfWires <= 9) {
              if (amphereCapacity <= 12) {
                showResult(60, 3.5);
              } else if (amphereCapacity <= 17) {
                showResult(60, 5.5);
              } else if (amphereCapacity <= 20) {
                showResult(60, 8);
              } else if (amphereCapacity <= 30) {
                showResult(60, 14);
              } else if (amphereCapacity <= 40) {
                showResult(60, 22);
              } else if (amphereCapacity <= 50) {
                showResult(60, 30);
              } else if (amphereCapacity <= 55) {
                showResult(60, 38);
              } else if (amphereCapacity <= 65) {
                showResult(60, 50);
              } else if (amphereCapacity <= 75) {
                showResult(60, 60);
              } else if (amphereCapacity <= 90) {
                showResult(60, 80);
              } else if (amphereCapacity <= 105) {
                showResult(60, 100);
              } else {
                resultText.value = "Error 4";
              }
            } else {
              resultText.value = "Error 5";
            }
          } else if (degree === "75") {
            if (numberOfWires >= 1 && numberOfWires <= 3) {
              if (amphereCapacity <= 25) {
                showResult(75, 3.5);
              } else if (amphereCapacity <= 34) {
                showResult(75, 5.5);
              } else if (amphereCapacity <= 46) {
                showResult(75, 8);
              } else if (amphereCapacity <= 63) {
                showResult(75, 14);
              } else if (amphereCapacity <= 81) {
                showResult(75, 22);
              } else if (amphereCapacity <= 101) {
                showResult(75, 30);
              } else if (amphereCapacity <= 114) {
                showResult(75, 38);
              } else if (amphereCapacity <= 134) {
                showResult(75, 50);
              } else if (amphereCapacity <= 155) {
                showResult(75, 60);
              } else if (amphereCapacity <= 181) {
                showResult(75, 80);
              } else if (amphereCapacity <= 210) {
                showResult(75, 100);
              } else if (amphereCapacity <= 238) {
                showResult(75, 125);
              } else if (amphereCapacity <= 269) {
                showResult(75, 150);
              } else if (amphereCapacity <= 310) {
                showResult(75, 200);
              } else if (amphereCapacity <= 358) {
                showResult(75, 250);
              } else if (amphereCapacity <= 407) {
                showResult(75, 325);
              } else if (amphereCapacity <= 459) {
                showResult(75, 400);
              } else if (amphereCapacity <= 504) {
                showResult(75, 500);
              } else {
                resultText.value = "Error 6";
              }
            } else if (numberOfWires == 4) {
              if (amphereCapacity <= 22) {
                showResult(75, 3.5);
              } else if (amphereCapacity <= 30) {
                showResult(75, 5.5);
              } else if (amphereCapacity <= 41) {
                showResult(75, 8);
              } else if (amphereCapacity <= 57) {
                showResult(75, 14);
              } else if (amphereCapacity <= 73) {
                showResult(75, 22);
              } else if (amphereCapacity <= 90) {
                showResult(75, 30);
              } else if (amphereCapacity <= 103) {
                showResult(75, 38);
              } else if (amphereCapacity <= 121) {
                showResult(75, 50);
              } else if (amphereCapacity <= 139) {
                showResult(75, 60);
              } else if (amphereCapacity <= 163) {
                showResult(75, 80);
              } else if (amphereCapacity <= 189) {
                showResult(75, 100);
              } else if (amphereCapacity <= 214) {
                showResult(75, 125);
              } else if (amphereCapacity <= 242) {
                showResult(75, 150);
              } else if (amphereCapacity <= 279) {
                showResult(75, 200);
              } else if (amphereCapacity <= 322) {
                showResult(75, 250);
              } else if (amphereCapacity <= 367) {
                showResult(75, 325);
              } else {
                resultText.value = "Error 7";
              }
            } else if (numberOfWires >= 5 && numberOfWires <= 6) {
              if (amphereCapacity <= 19) {
                showResult(75, 3.5);
              } else if (amphereCapacity <= 27) {
                showResult(75, 5.5);
              } else if (amphereCapacity <= 37) {
                showResult(75, 8);
              } else if (amphereCapacity <= 50) {
                showResult(75, 14);
              } else if (amphereCapacity <= 65) {
                showResult(75, 22);
              } else if (amphereCapacity <= 80) {
                showResult(75, 30);
              } else if (amphereCapacity <= 92) {
                showResult(75, 38);
              } else if (amphereCapacity <= 107) {
                showResult(75, 50);
              } else if (amphereCapacity <= 124) {
                showResult(75, 60);
              } else if (amphereCapacity <= 145) {
                showResult(75, 80);
              } else if (amphereCapacity <= 168) {
                showResult(75, 100);
              } else if (amphereCapacity <= 191) {
                showResult(75, 125);
              } else if (amphereCapacity <= 216) {
                showResult(75, 150);
              } else if (amphereCapacity <= 248) {
                showResult(75, 200);
              } else {
                resultText.value = "Error 8";
              }
            } else if (numberOfWires >= 7 && numberOfWires <= 9) {
              if (amphereCapacity <= 17) {
                showResult(75, 3.5);
              } else if (amphereCapacity <= 24) {
                showResult(75, 5.5);
              } else if (amphereCapacity <= 32) {
                showResult(75, 8);
              } else if (amphereCapacity <= 44) {
                showResult(75, 14);
              } else if (amphereCapacity <= 57) {
                showResult(75, 22);
              } else if (amphereCapacity <= 70) {
                showResult(75, 30);
              } else if (amphereCapacity <= 80) {
                showResult(75, 38);
              } else if (amphereCapacity <= 94) {
                showResult(75, 50);
              } else if (amphereCapacity <= 108) {
                showResult(75, 60);
              } else if (amphereCapacity <= 127) {
                showResult(75, 80);
              } else if (amphereCapacity <= 147) {
                showResult(75, 100);
              } else if (amphereCapacity <= 167) {
                showResult(75, 125);
              } else {
                resultText.value = "Error 9";
              }
            } else {
              resultText.value = "Error 10";
            }
          } else if (degree === "90") {
            if (numberOfWires >= 1 && numberOfWires <= 3) {
              if (amphereCapacity <= 30) {
                showResult(90, 3.5);
              } else if (amphereCapacity <= 39) {
                showResult(90, 5.5);
              } else if (amphereCapacity <= 51) {
                showResult(90, 8);
              } else if (amphereCapacity <= 74) {
                showResult(90, 14);
              } else if (amphereCapacity <= 93) {
                showResult(90, 22);
              } else if (amphereCapacity <= 116) {
                showResult(90, 30);
              } else if (amphereCapacity <= 130) {
                showResult(90, 38);
              } else if (amphereCapacity <= 155) {
                showResult(90, 50);
              } else if (amphereCapacity <= 176) {
                showResult(90, 60);
              } else if (amphereCapacity <= 208) {
                showResult(90, 80);
              } else if (amphereCapacity <= 242) {
                showResult(90, 100);
              } else if (amphereCapacity <= 277) {
                showResult(90, 125);
              } else if (amphereCapacity <= 309) {
                showResult(90, 150);
              } else if (amphereCapacity <= 359) {
                showResult(90, 200);
              } else if (amphereCapacity <= 413) {
                showResult(90, 250);
              } else if (amphereCapacity <= 471) {
                showResult(90, 325);
              } else if (amphereCapacity <= 531) {
                showResult(90, 400);
              } else if (amphereCapacity <= 581) {
                showResult(90, 500);
              } else {
                resultText.value = "Error 11";
              }
            } else if (numberOfWires == 4) {
              if (amphereCapacity <= 27) {
                showResult(90, 3.5);
              } else if (amphereCapacity <= 32) {
                showResult(90, 5.5);
              } else if (amphereCapacity <= 46) {
                showResult(90, 8);
              } else if (amphereCapacity <= 67) {
                showResult(90, 14);
              } else if (amphereCapacity <= 84) {
                showResult(90, 22);
              } else if (amphereCapacity <= 104) {
                showResult(90, 30);
              } else if (amphereCapacity <= 117) {
                showResult(90, 38);
              } else if (amphereCapacity <= 140) {
                showResult(90, 50);
              } else if (amphereCapacity <= 159) {
                showResult(90, 60);
              } else if (amphereCapacity <= 187) {
                showResult(90, 80);
              } else if (amphereCapacity <= 218) {
                showResult(90, 100);
              } else if (amphereCapacity <= 249) {
                showResult(90, 125);
              } else if (amphereCapacity <= 278) {
                showResult(90, 150);
              } else if (amphereCapacity <= 372) {
                showResult(90, 200);
              } else if (amphereCapacity <= 424) {
                showResult(90, 250);
              } else {
                resultText.value = "Error 12";
              }
            } else if (numberOfWires >= 5 && numberOfWires <= 6) {
              if (amphereCapacity <= 24) {
                showResult(90, 3.5);
              } else if (amphereCapacity <= 31) {
                showResult(90, 5.5);
              } else if (amphereCapacity <= 41) {
                showResult(90, 8);
              } else if (amphereCapacity <= 59) {
                showResult(90, 14);
              } else if (amphereCapacity <= 74) {
                showResult(90, 22);
              } else if (amphereCapacity <= 93) {
                showResult(90, 30);
              } else if (amphereCapacity <= 104) {
                showResult(90, 38);
              } else if (amphereCapacity <= 124) {
                showResult(90, 50);
              } else if (amphereCapacity <= 141) {
                showResult(90, 60);
              } else if (amphereCapacity <= 167) {
                showResult(90, 80);
              } else if (amphereCapacity <= 194) {
                showResult(90, 100);
              } else if (amphereCapacity <= 221) {
                showResult(90, 125);
              } else if (amphereCapacity <= 247) {
                showResult(90, 150);
              } else if (amphereCapacity <= 287) {
                showResult(90, 200);
              } else {
                resultText.value = "Error 13";
              }
            } else if (numberOfWires >= 7 && numberOfWires <= 9) {
              if (amphereCapacity <= 21) {
                showResult(90, 3.5);
              } else if (amphereCapacity <= 27) {
                showResult(90, 5.5);
              } else if (amphereCapacity <= 36) {
                showResult(90, 8);
              } else if (amphereCapacity <= 52) {
                showResult(90, 14);
              } else if (amphereCapacity <= 65) {
                showResult(90, 22);
              } else if (amphereCapacity <= 81) {
                showResult(90, 30);
              } else if (amphereCapacity <= 91) {
                showResult(90, 38);
              } else if (amphereCapacity <= 109) {
                showResult(90, 50);
              } else if (amphereCapacity <= 123) {
                showResult(90, 60);
              } else if (amphereCapacity <= 146) {
                showResult(90, 80);
              } else if (amphereCapacity <= 170) {
                showResult(90, 100);
              } else if (amphereCapacity <= 194) {
                showResult(90, 125);
              } else {
                resultText.value = "Error 14";
              }
            } else {
              resultText.value = "Error 15";
            }
          } else {
            resultText.value = "輸入錯誤數值";
          }
        });
    </script>
  </body>
</html>
