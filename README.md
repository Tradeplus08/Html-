<html> 
 <head> 
  <style>
        /* CSS Code */
        .hero {
            text-align: center;
            padding: 20px;
            background-color: #f2f2f2;
        }
        .feature {
            background-color: #e0e0e0;
            margin: 10px;
            padding: 15px;
            border-radius: 5px;
        }
    </style> 
 </head> 
 <body> 
  <section class="hero"> 
   <h2>Welcome to Trade Plus</h2> 
   <p>Start trading with the best platform!</p> <button onclick="startTrading()">Get Started</button> 
  </section> 
  <section class="features"> 
   <div class="feature"> 
    <h3>Real-time Stock Tracking</h3> 
    <p>Track stock prices live and make informed decisions.</p> 
   </div> 
   <div class="feature"> 
    <h3>Trading Tools</h3> 
    <p>Use powerful tools to trade effectively and efficiently.</p> 
   </div> 
   <div class="feature"> 
    <h3>Secure Account</h3> 
    <p>Your account and data are fully secured with encryption.</p> 
   </div> 
  </section> 
  <footer> 
   <p>© 2024 Trade Plus. All rights reserved.</p> 
  </footer> 
  <script>
        // JavaScript Code
        function startTrading() {
            alert("Welcome to Trade Plus! Let's start trading.");
        }
    </script> <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trade Plus</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <section class="hero">
        <h2>Welcome to Trade Plus</h2>
        <p>Start trading with the best platform!</p>
        <button onclick="startTrading()">Get Started</button>
    </section>

    <section class="features">
        <div class="feature">
            <h3>Real-time Stock Tracking</h3>
            <p>Track stock prices live and make informed decisions.</p>
        </div>
        <div class="feature">
            <h3>Trading Tools</h3>
            <p>Use powerful tools to trade effectively and efficiently.</p>
        </div>
        <div class="feature">
            <h3>Secure Account</h3>
            <p>Your account and data are fully secured with encryption.</p>
        </div>
    </section>

    <!-- New Section for Live Stock Data -->
    <section class="stock-data">
        <h3>Live Stock Price</h3>
        <p id="stock-price">Loading...</p>
    </section>

    <footer>
        <p>&copy; 2024 Trade Plus. All rights reserved.</p>
    </footer>

    <!-- JavaScript for API Call -->
    <script>
        async function fetchStockData() {
            const apiKey = 'YOUR_API_KEY_HERE'WUOXTE9RXQDUGVIQ
            const symbol = 'AAPL'; // आप यहां कोई भी स्टॉक का नाम डाल सकते हैं, जैसे कि AAPL (Apple)

            try {
                const response = await fetch(`https://www.alphavantage.co/query?function=TIME_SERIES_INTRADAY&symbol=${symbol}&interval=1min&apikey=${apiKey}`);
                const data = await response.json();

                if (data['Time Series (1min)']) {
                    const latestTime = Object.keys(data['Time Series (1min)'])[0];
                    const latestData = data['Time Series (1min)'][latestTime];
                    const price = latestData['1. open'];

                    document.getElementById('stock-price').innerText = `Latest Price of ${symbol}: $${price}`;
                } else {
                    document.getElementById('stock-price').innerText = 'Stock data not available';
                }
            } catch (error) {
                console.error('Error fetching stock data:', error);
                document.getElementById('stock-price').innerText = 'Error fetching stock data';
            }
        }

        fetchStockData();
    </script>
</body>
</html>

  
 </body>
</html>
