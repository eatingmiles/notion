<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Currency Converter</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
        }
        .converter {
            max-width: 400px;
            margin: 0 auto;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 8px;
        }
        .converter input, .converter select, .converter button {
            width: 100%;
            margin: 10px 0;
            padding: 10px;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <div class="converter">
        <h2>Currency Converter</h2>
        <input type="number" id="amount" placeholder="Amount" />
        <select id="fromCurrency">
            <option value="EUR">EUR</option>
            <option value="USD">USD</option>
            <!-- Add more currencies as needed -->
        </select>
        <select id="toCurrency">
            <option value="USD">USD</option>
            <option value="EUR">EUR</option>
            <!-- Add more currencies as needed -->
        </select>
        <input type="number" id="exchangeRate" placeholder="Exchange Rate" />
        <button onclick="convertCurrency()">Convert</button>
        <p id="result"></p>
    </div>

    <script>
        function convertCurrency() {
            const amount = document.getElementById('amount').value;
            const fromCurrency = document.getElementById('fromCurrency').value;
            const toCurrency = document.getElementById('toCurrency').value;
            const exchangeRate = document.getElementById('exchangeRate').value;

            if (amount === '' || isNaN(amount)) {
                alert('Please enter a valid amount');
                return;
            }

            if (exchangeRate === '' || isNaN(exchangeRate)) {
                alert('Please enter a valid exchange rate');
                return;
            }

            const convertedAmount = (amount * exchangeRate).toFixed(2);
            document.getElementById('result').innerText = `${amount} ${fromCurrency} = ${convertedAmount} ${toCurrency}`;
        }
    </script>
</body>
</html>

