
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kamakshi | Portfolio</title>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Poppins:wght@300;400;500&display=swap');

  body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(135deg, #000000, #1a1a1a);
    color: #f5f5f5;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  header {
    width: 100%;
    text-align: center;
    padding: 60px 0 30px;
  }

  h1 {
    font-family: 'Playfair Display', serif;
    font-size: 3.5em;
    background: linear-gradient(90deg, #d4af37, #b8860b);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    text-shadow: 0 0 20px rgba(212,175,55,0.4);
    letter-spacing: 3px;
  }

  section {
    max-width: 800px;
    width: 90%;
    background: rgba(20, 20, 20, 0.7);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(212,175,55,0.3);
    border-radius: 20px;
    padding: 40px;
    box-shadow: 0 0 25px rgba(212,175,55,0.2);
    margin-bottom: 40px;
  }

  h2 {
    font-family: 'Playfair Display', serif;
    color: #d4af37;
    border-bottom: 1px solid rgba(212,175,55,0.4);
    padding-bottom: 10px;
    margin-bottom: 25px;
    font-size: 1.6em;
  }

  p {
    font-size: 1.05em;
    line-height: 1.7em;
    color: #eaeaea;
  }

  .skills {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    margin-top: 20px;
  }

  .skill-box {
    border: 1px solid rgba(212,175,55,0.6);
    color: #f5f5f5;
    padding: 10px 18px;
    border-radius: 8px;
    font-size: 0.95em;
    background: rgba(212,175,55,0.08);
    transition: 0.3s ease;
  }

  .skill-box:hover {
    background: rgba(212,175,55,0.25);
    transform: translateY(-3px);
  }

  form {
    display: flex;
    flex-direction: column;
    gap: 15px;
  }

  input, textarea {
    padding: 12px;
    border-radius: 8px;
    border: 1px solid rgba(212,175,55,0.4);
    font-family: 'Poppins', sans-serif;
    font-size: 1em;
    outline: none;
    background-color: rgba(255,255,255,0.1);
    color: white;
  }

  button {
    background: linear-gradient(90deg, #d4af37, #b8860b);
    border: none;
    padding: 12px;
    color: black;
    border-radius: 8px;
    font-size: 1em;
    font-weight: 500;
    cursor: pointer;
    transition: 0.3s ease;
  }

  button:hover {
    background: linear-gradient(90deg, #b8860b, #d4af37);
    box-shadow: 0 0 15px rgba(212,175,55,0.3);
  }

  footer {
    margin-bottom: 40px;
  }

  .socials {
    display: flex;
    justify-content: center;
    gap: 25px;
  }

  .socials a img {
    width: 34px;
    opacity: 0.8;
    transition: 0.3s ease;
    filter: drop-shadow(0 0 5px rgba(212,175,55,0.2));
  }

  .socials a img:hover {
    opacity: 1;
    transform: scale(1.1);
    filter: drop-shadow(0 0 10px rgba(212,175,55,0.4));
  }
</style>
</head>

<body>
  <header>
    <h1>Kamakshi</h1>
  </header>

  <section>
    <h2>About Me</h2>
    <p>I like coding and am very interested in web development. This is my first website that I've created.</p>

    <div class="skills">
      <div class="skill-box">HTML</div>
      <div class="skill-box">CSS</div>
      <div class="skill-box">JavaScript</div>
      <div class="skill-box">Web Design</div>
      <div class="skill-box">Creative Writing</div>
      <div class="skill-box">Gaming</div>
    </div>
  </section>

  <section>
    <h2>Contact Me</h2>
    <form action="https://formspree.io/f/yourformid" method="POST">
      <input type="text" name="name" placeholder="Your Name" required>
      <input type="email" name="_replyto" placeholder="Your Email" required>
      <textarea name="message" rows="4" placeholder="Your Message" required></textarea>
      <button type="submit">Send Message</button>
    </form>
  </section>

  <footer>
    <div class="socials">
      <a href="https://github.com/yourusername"><img src="https://cdn-icons-png.flaticon.com/512/733/733553.png" alt="GitHub"></a>
      <a href="https://www.linkedin.com/in/yourusername"><img src="https://cdn-icons-png.flaticon.com/512/733/733561.png" alt="LinkedIn"></a>
      <a href="https://www.instagram.com/yourusername"><img src="https://cdn-icons-png.flaticon.com/512/2111/2111463.png" alt="Instagram"></a>
      <a href="https://www.snapchat.com/add/yourusername"><img src="https://cdn-icons-png.flaticon.com/512/2111/2111628.png" alt="Snapchat"></a>
    </div>
  </footer>
</body>
</html>
