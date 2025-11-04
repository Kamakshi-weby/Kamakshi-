<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Kamakshi Singh — Connect</title>

  <!-- Google font -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

  <style>
    :root{
      --lav-1: #f3eaff;
      --lav-2: #e6e6fa;
      --lav-3: #c8a2c8;
      --accent: #4b0082;
      --muted: #444;
      --card: #ffffff;
      --radius: 12px;
      --maxw: 920px;
    }

    *{box-sizing:border-box}
    body{
      margin:0;
      font-family:"Poppins",system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial;
      color:var(--muted);
      background: linear-gradient(135deg, var(--lav-1) 0%, var(--lav-2) 45%, var(--lav-3) 100%);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      display:flex;
      justify-content:center;
      padding:40px 18px;
    }

    .wrap{
      width:100%;
      max-width:var(--maxw);
      background:transparent;
      display:grid;
      grid-template-columns:1fr 420px;
      gap:32px;
      align-items:start;
    }

    @media (max-width:880px){
      .wrap{grid-template-columns:1fr; padding:0 8px}
    }

    /* Left column (intro) */
    .intro{
      padding:36px;
      background: rgba(255,255,255,0.6);
      border-radius:var(--radius);
      box-shadow:0 8px 30px rgba(75,0,130,0.08);
      backdrop-filter: blur(4px);
    }

    .avatar{
      width:88px;
      height:88px;
      border-radius:16px;
      background:linear-gradient(180deg, rgba(255,255,255,0.6), rgba(255,255,255,0.15));
      display:inline-block;
      margin-bottom:18px;
      overflow:hidden;
    }

    h1{
      margin:0;
      font-size:1.6rem;
      color:var(--accent);
      letter-spacing:0.2px;
    }

    .subtitle{
      margin:8px 0 18px 0;
      font-weight:600;
      color:#333;
      font-size:0.95rem;
    }

    p.lead{
      margin:0 0 22px 0;
      line-height:1.6;
      color:var(--muted);
      font-size:1rem;
    }

    .skills{
      display:flex;
      flex-wrap:wrap;
      gap:8px;
      margin-top:12px;
    }

    .badge{
      background:rgba(75,0,130,0.08);
      color:var(--accent);
      padding:6px 10px;
      border-radius:999px;
      font-weight:600;
      font-size:0.85rem;
    }

    /* Right column (form) */
    .card{
      background:var(--card);
      border-radius:var(--radius);
      padding:28px;
      box-shadow:0 10px 30px rgba(0,0,0,0.06);
    }

    .form-title{
      margin:0 0 14px 0;
      color:var(--accent);
      font-size:1.05rem;
      font-weight:700;
    }

    label{
      display:block;
      margin:10px 0 6px 0;
      font-size:0.9rem;
      color:#333;
    }

    input[type="text"],
    input[type="email"],
    textarea{
      width:100%;
      padding:12px 14px;
      border-radius:10px;
      border:1px solid #e6e6e6;
      font-family:inherit;
      font-size:0.95rem;
      resize:vertical;
      background: #fbfbfd;
    }

    textarea{min-height:120px}

    .actions{
      margin-top:14px;
      display:flex;
      gap:12px;
      align-items:center;
    }

    button.send{
      background:linear-gradient(90deg,var(--lav-3),#b583b1);
      border:none;
      color:white;
      padding:11px 18px;
      border-radius:10px;
      font-weight:600;
      cursor:pointer;
      box-shadow:0 6px 18px rgba(180,120,200,0.16);
    }

    button.send:active{transform:translateY(1px)}

    .note{
      font-size:0.88rem;
      color:#666;
    }

    .status{
      margin-top:12px;
      font-size:0.95rem;
      padding:10px 12px;
      border-radius:10px;
      display:none;
    }

    .status.success{background:rgba(72,187,120,0.12); color:#147a2b; display:block}
    .status.error{background:rgba(230,70,70,0.08); color:#b72a2a; display:block}

    /* bottom contact links */
    .contacts{
      grid-column:1 / -1;
      margin-top:18px;
      display:flex;
      justify-content:center;
      gap:22px;
      align-items:center;
      padding-top:6px;
    }

    .contacts a{
      text-decoration:none;
      color:var(--accent);
      font-weight:600;
      display:inline-flex;
      gap:8px;
      align-items:center;
      padding:8px 12px;
      border-radius:10px;
      background: rgba(255,255,255,0.62);
      box-shadow:0 6px 18px rgba(75,0,130,0.04);
    }

    .contacts svg{width:18px;height:18px;display:block}

    footer{
      margin-top:20px;
      text-align:center;
      font-size:0.9rem;
      color:#333;
      opacity:0.9;
    }

    /* small */
    .small-muted{font-size:0.9rem;color:#666}
  </style>
</head>
<body>
  <div class="wrap" role="main">
    <section class="intro" aria-label="About Kamakshi">
      <div style="display:flex;gap:18px;align-items:center">
        <div class="avatar" aria-hidden="true">
          <!-- optional avatar: you can replace <img> src with your own small image -->
          <img src="https://avatars.githubusercontent.com/u/583231?v=4" alt="Kamakshi avatar" style="width:100%;height:100%;object-fit:cover">
        </div>
        <div>
          <h1>Kamakshi Singh</h1>
          <div class="subtitle">BCA Student — Aspiring Web Developer</div>
        </div>
      </div>

      <p class="lead">
        I am a first-year Bachelor of Computer Applications (BCA) student with a growing interest in web development and programming.
        I’m learning the fundamentals of HTML, CSS, Java and Python and enjoy combining creativity with logical problem solving to build user-focused web experiences.
        I’m open to collaboration, feedback, and opportunities to grow.
      </p>

      <div class="skills" aria-hidden="true">
        <span class="badge">HTML</span>
        <span class="badge">CSS</span>
        <span class="badge">Java (learning)</span>
        <span class="badge">Python (learning)</span>
        <span class="badge">Web Design</span>
      </div>
    </section>

    <aside class="card" aria-label="Contact form">
      <h3 class="form-title">Send Me a Message</h3>

      <!--
        IMPORTANT:
        Replace the FORMSPREE_ENDPOINT below with your own Formspree URL.
        1) Sign up or log in at https://formspree.io
        2) Create a new form and connect your email
        3) Formspree gives you a URL like: https://formspree.io/f/xxxxxxx
        4) Replace FORMSPREE_ENDPOINT value in the script below and in the form's "action" attribute if you prefer non-AJAX.
      -->

      <form id="contact-form" action="https://formspree.io/f/your-form-id" method="POST" novalidate>
        <label for="name">Your name</label>
        <input id="name" name="name" type="text" placeholder="How should I address you?" required>

        <label for="email">Your email</label>
        <input id="email" name="_replyto" type="email" placeholder="name@example.com" required>

        <label for="message">Message</label>
        <textarea id="message" name="message" placeholder="Write your message..." required></textarea>

        <div class="actions">
          <button type="submit" class="send">Send Message</button>
          <div class="note small-muted">You will receive a reply at the email you provide.</div>
        </div>

        <div id="status" class="status" role="status" aria-live="polite"></div>
      </form>
    </aside>

    <div class="contacts" aria-label="Social links">
      <a href="https://instagram.com/kamakshiii_singh" target="_blank" rel="noopener noreferrer">
        <!-- Instagram SVG -->
        <svg viewBox="0 0 24 24" fill="none" aria-hidden="true"><path d="M7 2h10a5 5 0 0 1 5 5v10a5 5 0 0 1-5 5H7a5 5 0 0 1-5-5V7a5 5 0 0 1 5-5z" stroke="currentColor" stroke-width="1.3" stroke-linecap="round" stroke-linejoin="round"></path><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z" stroke="currentColor" stroke-width="1.3" stroke-linecap="round" stroke-linejoin="round"/></svg>
        Instagram
      </a>

      <a href="https://snapchat.com/add/kaaaaaaashu" target="_blank" rel="noopener noreferrer">
        <!-- simple ghost icon -->
        <svg viewBox="0 0 24 24" fill="none" aria-hidden="true"><path d="M12 2c2.8 0 4 1.2 4 3.2V8c0 .9.6 1.7 1.4 2 1.2.5 1.6 1.9 1.6 3.6v3.2c0 1.1-.9 2-2 2h-1.2c-.5 0-.9.3-1.1.7-.5.9-1.6 1.3-2.6 1.3s-2.1-.4-2.6-1.3c-.2-.4-.6-.7-1.1-.7H8.6c-1.1 0-2-.9-2-2V14.8c0-1.7.4-3.1 1.6-3.6.8-.3 1.4-1.1 1.4-2V5.2C8 3.2 9.2 2 12 2z" stroke="currentColor" stroke-width="1.1" stroke-linejoin="round"/></svg>
        Snapchat
      </a>

      <a href="http://linkedin.com/in/kamakshi-singh-40685a395" target="_blank" rel="noopener noreferrer">
        <!-- LinkedIn -->
        <svg viewBox="0 0 24 24" fill="none" aria-hidden="true"><rect x="3" y="3" width="18" height="18" rx="2" stroke="currentColor" stroke-width="1.2"/><path d="M8 11v6" stroke="currentColor" stroke-width="1.3" stroke-linecap="round"/><path d="M8 8v.01" stroke="currentColor" stroke-width="1.3" stroke-linecap="round"/><path d="M12 11v6" stroke="currentColor" stroke-width="1.3" stroke-linecap="round"/><path d="M16 11v6" stroke="currentColor" stroke-width="1.3" stroke-linecap="round"/></svg>
        LinkedIn
      </a>

      <a href="mailto:kamakshisinghranchi1@gmail.com" target="_blank" rel="noopener noreferrer">
        <!-- Mail -->
        <svg viewBox="0 0 24 24" fill="none" aria-hidden="true"><path d="M3 7.5v9A2.5 2.5 0 0 0 5.5 19h13A2.5 2.5 0 0 0 21 16.5v-9" stroke="currentColor" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"/><path d="M21 7.5L12 13 3 7.5" stroke="currentColor" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"/></svg>
        Email
      </a>
    </div>

    <footer style="grid-column:1 / -1">
      <div class="small-muted">Made with 💜 by Kamakshi • © <span id="year"></span></div>
    </footer>
  </div>

  <script>
    document.getElementById('year').textContent = new Date().getFullYear();

    // --- FORM HANDLING (AJAX to Formspree)
    const form = document.getElementById('contact-form');
    const statusEl = document.getElementById('status');

    // Replace this placeholder with your actual Formspree endpoint.
    // Example endpoint: "https://formspree.io/f/movqazde"
    const FORMSPREE_ENDPOINT = "https://formspree.io/f/your-form-id";

    form.addEventListener('submit', async (e) => {
      e.preventDefault();
      statusEl.style.display = 'none';
      statusEl.className = 'status';
      const data = new FormData(form);

      // Basic client-side validation (extra)
      if (!data.get('name') || !data.get('_replyto') || !data.get('message')) {
        statusEl.textContent = 'Please fill all fields before sending.';
        statusEl.classList.add('error');
        statusEl.style.display = 'block';
        return;
      }

      try {
        const resp = await fetch(FORMSPREE_ENDPOINT, {
          method: 'POST',
          headers: { 'Accept': 'application/json' },
          body: data
        });

        if (resp.ok) {
          // success
          statusEl.textContent = 'Thanks — your message has been sent. I will reply soon!';
          statusEl.classList.add('success');
          statusEl.style.display = 'block';
          form.reset();
        } else {
          const json = await resp.json();
          throw new Error(json.error || 'Submission failed');
        }
      } catch (err) {
        statusEl.textContent = 'There was an error sending your message. Please try again later.';
        statusEl.classList.add('error');
        statusEl.style.display = 'block';
        console.error(err);
      }
    });
  </script>
</body>
</html>
