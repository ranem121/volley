<!DOCTYPE html>
<html>
<head>
  <title>Beach Volleyball Countdown</title>
  <style>
    body { 
      font-family: Arial; 
      text-align: center; 
      background: #FF6B6B; 
      color: white; 
      padding: 50px;
    }
    #countdown { 
      font-size: 3em; 
      font-weight: bold; 
    }
  </style>
</head>
<body>
  <h1>⏳ REGISTRATION ENDS IN:</h1>
  <div id="countdown">
    <span id="days"></span>d 
    <span id="hours"></span>h 
    <span id="minutes"></span>m 
    <span id="seconds"></span>s
  </div>

  <script>
    const endDate = new Date("2025-05-01T23:59:59").getTime();
    const timer = setInterval(() => {
      const now = new Date().getTime();
      const diff = endDate - now;
      document.getElementById("days").innerText = Math.floor(diff / (86400000));
      document.getElementById("hours").innerText = Math.floor((diff % 86400000) / 3600000);
      document.getElementById("minutes").innerText = Math.floor((diff % 3600000) / 60000);
      document.getElementById("seconds").innerText = Math.floor((diff % 60000) / 1000);
      if (diff < 0) clearInterval(timer);
    }, 1000);
  </script>
</body>
</html>
