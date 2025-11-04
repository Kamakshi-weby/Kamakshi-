
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kamakshi | Portfolio</title>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&family=Poppins:wght@300;400;500&display=swap');

  body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(135deg, #f3f0f5, #d9cce3, #fffaf3);
    color: #333;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  header {
    width: 100%;
    text-align: center;
    padding: 50px 0 20px;
  }

  h1 {
    font-family: 'Playfair Display', serif;
    font-size: 3em;
    background: linear-gradient(90deg, #d4af37, #c0a060);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    text-shadow: 0 0 25px rgba(212,175,55,0.2);
    letter-spacing: 2px;
  }

  .ghost-icon {
    width: 40px;
    vertical-align: middle;
    margin-left: 10px;
    opacity: 0.8;
  }

  section {
    max-width: 700px;
    width: 90%;
    background: rgba(255,255,255,0.4);
    backdrop-filter: blur(15px);
    border: 1px solid rgba(255, 215, 0, 0.3);
    border-radius: 20px;
    padding: 30px 40px;
    box-shadow: 0 0 25px rgba(212,175,55,0.15);
    margin-bottom: 40px;
  }

  h2 {
    font-family: 'Playfair Display', serif;
    color: #b18f3a;
    border-bottom: 1px solid rgba(212,175,55,0.3);
    padding-bottom: 10px;
    margin-bottom: 20px;
  }

  p {
    font-size: 1.05em;
    line-height: 1.7em;
    color: #444;
  }

  ul {
    list-style: none;
    padding: 0;
  }

  ul li::before {
    content: "• ";
    color: #b18f3a;
    font-weight: bold;
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
    background-color: rgba(255,255,255,0.7);
  }

  button {
    background: linear-gradient(90deg, #d4af37, #c0a060);
    border: none;
    padding: 12px;
    color: white;
    border-radius: 8px;
    font-size: 1em;
    cursor: pointer;
    transition: 0.3s ease;
  }

  button:hover {
    background: linear-gradient(90deg, #c0a060, #d4af37);
    box-shadow: 0 0 15px rgba(212,175,55,0.3);
  }

  footer {
    margin-bottom: 30px;
  }

  .socials {
    display: flex;
    justify-content: center;
    gap: 25px;
  }

  .socials a img {
    width: 32px;
    opacity: 0.8;
    transition: 0.3s ease;
  }

  .socials a img:hover {
    opacity: 1;
    transform: scale(1.1);
  }

</style>
</head>

<body>
  <header>
    <h1>
      Kamakshi 
      <img class="ghost-icon" src="https://cdn-icons-png.flaticon.com/512/992/992703.png" alt="Ghost">
    </h1>
  </header>

  <section>
    <h2>About Me</h2>
    <p>I like coding and am very interested in web development. This is my first website that I've created.</p>
  </section>

  <section>
    <h2>Skills & Interests</h2>
    <ul>
      <li>Web Development (HTML, CSS, JavaScript)</li>
      <li>Creative Writing</li>
      <li>Gaming & Design</li>
    </ul>
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
    </div>
  </footer>
</body>
</html>
