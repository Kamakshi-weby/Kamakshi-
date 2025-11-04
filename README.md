
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kamakshi’s Ghosty Realm</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Cinzel+Decorative:wght@700&family=Raleway:wght@300&display=swap');

  body {
    margin: 0;
    height: 100vh;
    background: radial-gradient(circle at top left, #3c294d, #5f4383, #2a183b);
    font-family: 'Raleway', sans-serif;
    color: #fff;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }

  .glassy-box {
    background: rgba(255, 255, 255, 0.08);
    backdrop-filter: blur(15px);
    border: 1px solid rgba(255, 215, 0, 0.3);
    border-radius: 20px;
    padding: 40px;
    box-shadow: 0 0 30px rgba(255, 215, 0, 0.2);
    text-align: center;
  }

  h1 {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 3em;
    background: linear-gradient(90deg, #ffd700, #d4af37);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    text-shadow: 0 0 15px rgba(255, 215, 0, 0.3);
    margin-bottom: 20px;
  }

  .ghost {
    width: 120px;
    animation: float 3s ease-in-out infinite;
    filter: drop-shadow(0 0 15px rgba(255,255,255,0.5));
  }

  @keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-15px); }
  }

  p {
    font-size: 1.1em;
    color: #f8e8ff;
    margin-top: 20px;
    text-shadow: 0 0 10px rgba(255,255,255,0.2);
  }
</style>
</head>
<body>
  <div class="glassy-box">
    <h1>Kamakshi</h1>
    <img class="ghost" src="https://cdn-icons-png.flaticon.com/512/992/992703.png" alt="Cute Ghost">
    <p>Welcome to my dreamy, glassy ghost realm ✨</p>
  </div>
</body>
</html>