Hello world

<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>截面積計算器</title>
    <script>
        function calculateCrossSectionalArea() {
            // Get user input
            const nfbCapacity = parseFloat(document.getElementById('nfbCapacity').value);
            const insulationTemp = parseFloat(document.getElementById('insulationTemp').value);
            const conductorCount = parseInt(document.getElementById('conductorCount').value);
            
            // Example calculation for cross-sectional area (modify as needed)
            const area = (nfbCapacity / 100) * (conductorCount / 5) * (insulationTemp / 60);

            // Display the calculated cross-sectional area
            document.getElementById('calculatedArea').innerText = area.toFixed(2) + ' 平方公厘';
        }
    </script>
</head>
<body>
    <h1>截面積計算器</h1>
    <div>
        <label for="nfbCapacity">NFB 安培容量 (A):</label>
        <input type="number" id="nfbCapacity" value="100">
    </div>
    <div>
        <label for="insulationTemp">導線絕緣物溫度 (°C):</label>
        <input type="number" id="insulationTemp" value="60">
    </div>
    <div>
        <label for="conductorCount">導線數:</label>
        <input type="number" id="conductorCount" value="5">
    </div>
    <button onclick="calculateCrossSectionalArea()">計算</button>
    <div>
        <h2>結果</h2>
        <p>絞線截面積 (平方公厘): <span id="calculatedArea"></span></p>
    </div>
</body>
</html>
