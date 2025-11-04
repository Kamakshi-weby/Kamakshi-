
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome - Web Developer Portfolio</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400..700;1,400..700&family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
    
    <script src="https://kit.fontawesome.com/9780135d1f.js" crossorigin="anonymous"></script>

    <style>
        /* --- 1. GENERAL & TYPOGRAPHY --- */
        :root {
            --color-primary: #333d47;      /* Deep Charcoal / Dark Blue */
            --color-secondary: #f4f2f0;    /* Soft Cream/Off-White */
            --color-accent: #a4918e;       /* Muted Terracotta/Dusty Rose */
            --color-text: #555;
            --font-heading: 'Lora', serif;
            --font-body: 'Montserrat', sans-serif;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: var(--font-body);
            line-height: 1.6;
            color: var(--color-text);
            background-color: var(--color-secondary);
            scroll-behavior: smooth;
        }

        h1, h2, h3 {
            font-family: var(--font-heading);
            color: var(--color-primary);
            font-weight: 500;
        }

        h1 { font-size: 3.5rem; }
        h2 { font-size: 1.8rem; }
        h3 { font-size: 1.6rem; margin-bottom: 1.5rem; }

        a {
            color: var(--color-accent);
            text-decoration: none;
        }
        a:hover {
            color: var(--color-primary);
        }

        .container {
            max-width: 1100px;
            margin: auto;
            padding: 0 20px;
        }

        .section {
            padding: 80px 0;
        }
        
        /* --- 2. NAVIGATION (Simple fixed nav bar) --- */
        .navbar {
            background-color: var(--color-primary);
            color: var(--color-secondary);
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        
        .navbar .container {
            display: flex;
            justify-content: flex-end; /* Align links to the right */
        }
        
        .navbar a {
            color: var(--color-secondary);
            padding: 0 15px;
            font-weight: 600;
            text-transform: uppercase;
            font-size: 0.9rem;
            transition: color 0.3s;
        }
        
        .navbar a:hover {
            color: var(--color-accent);
        }


        /* --- 3. HERO SECTION STYLING --- */
        .hero {
            background-color: var(--color-primary);
            color: var(--color-secondary);
            min-height: 50vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 100px 20px;
        }

        .hero h1 {
            color: var(--color-secondary);
            margin-bottom: 0.5rem;
        }

        .hero h2 {
            color: var(--color-accent);
            font-weight: 300;
            margin-bottom: 1rem;
        }

        /* --- 4. ABOUT ME & SKILLS --- */
        .about-me {
            background-color: #fff;
            text-align: center;
        }
        
        .about-me p {
            max-width: 800px;
            margin: 0 auto 30px;
        }

        .skills-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin-top: 30px;
        }

        .skill-item {
            background-color: var(--color-secondary);
            color: var(--color-primary);
            padding: 10px 20px;
            border-radius: 5px;
            border: 1px solid var(--color-accent);
            font-weight: 600;
            text-transform: uppercase;
            font-size: 0.9rem;
            transition: background-color 0.3s, color 0.3s;
        }

        .skill-item:hover {
            background-color: var(--color-accent);
            color: #fff;
        }
        
        /* --- 5. PORTFOLIO (Placeholder Styling) --- */
        .portfolio {
             background-color: var(--color-secondary);
             text-align: center;
        }


        /* --- 6. CONTACT & FORM STYLING --- */
        .contact {
            background-color: #fff;
            text-align: center;
        }

        #contact-form {
            max-width: 600px;
            margin: 0 auto 30px;
            text-align: left;
            padding: 25px;
            border: 1px solid #ddd;
            background-color: var(--color-secondary);
            border-radius: 8px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-family: var(--font-body);
            font-size: 1rem;
        }

        .btn-submit {
            background-color: var(--color-accent);
            color: #fff;
            padding: 12px 25px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            transition: background-color 0.3s;
        }

        .btn-submit:hover {
            background-color: var(--color-primary);
        }

        .form-status {
            margin-top: 15px;
            font-weight: 600;
        }
        
        .contact-info-block {
            margin-top: 30px;
            line-height: 2.0;
            text-align: left;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .contact-info-block h4 {
            text-align: center;
        }
        
        .contact-info-block p {
            font-size: 1.1rem;
        }


        /* --- 7. FOOTER & SOCIALS --- */
        footer {
            background-color: var(--color-primary);
            color: var(--color-secondary);
            text-align: center;
            padding: 30px 20px;
            border-top: 5px solid var(--color-accent);
        }

        .socials {
            margin-bottom: 15px;
        }

        .socials a {
            color: var(--color-secondary);
            margin: 0 15px;
            transition: color 0.3s;
        }

        .socials a:hover {
            color: var(--color-accent);
        }
        
        /* --- 8. RESPONSIVE DESIGN --- */
        @media (max-width: 768px) {
            h1 { font-size: 2.5rem; }
            h2 { font-size: 1.5rem; }
            .section { padding: 60px 0; }
        }
    </style>
</head>
<body>

    <nav class="navbar">
        <div class="container">
            <a href="#about">About</a>
            <a href="#portfolio">Projects</a>
            <a href="#contact">Contact</a>
        </div>
    </nav>

    <header class="hero">
        <div class="hero-content">
            <h1>Welcome</h1>
            <p>I am passionate about transforming ideas into visually stunning and functional websites. My journey in web development is driven by a love,constantly learning and applying new techniques to solve digital challenges. I love coding and have been actively learning web development, aiming for seamless user experiences.</p>
            <h2>Skills: Web Developer | Design Enthusiast</h2>
            <p>HTML, CSS, JavaScript, Python, Java, Adobe & Canva, Blender (3D)</p>
        </div>
    </header>

    <section id="about" class="section about-me">
        <div class="container">
            <h3>About Me & My Skills</h3>
            <p>I am passionate about transforming ideas into visually stunning and functional websites. My journey in web development is driven by a love for **clean code** and **elegant design principles**, constantly learning and applying new techniques to solve digital challenges. I love coding and have been actively learning web development, aiming for seamless user experiences.</p>
            
            <div class="skills-grid">
                <div class="skill-item">HTML</div>
                <div class="skill-item">CSS</div>
                <div class="skill-item">JavaScript</div>
                <div class="skill-item">Python</div>
                <div class="skill-item">Java</div>
                <div class="skill-item">Adobe & Canva</div>
                <div class="skill-item">Blender (3D)</div>
            </div>
        </div>
    </section>

    <section id="portfolio" class="section portfolio">
        <div class="container">
            <h3>Featured Projects</h3>
            <p>A showcase of my recent coding and design projects will be displayed here soon. This section will demonstrate my abilities in responsive design and backend functionality.</p>
        </div>
    </section>

    <section id="contact" class="section contact">
        <div class="container">
            <h3>Get In Touch</h3>
            
            <form id="contact-form" action="YOUR_FORMSPREE_ENDPOINT" method="POST">
                <div class="form-group">
                    <label for="name">Name</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" name="_replyto" required>
                </div>
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea id="message" name="message" rows="5" required></textarea>
                </div>
                <button type="submit" class="btn-submit">Send Message</button>
                <p class="form-status" id="form-status"></p>
            </form>
            
            <div class="contact-info-block">
                <h4>✨ Contact Info</h4>
                <p>
                    <i class="fas fa-envelope"></i> 📧 **Email:** <a href="mailto:kamakshisinghranchi1@gmail.com">kamakshisinghranchi1@gmail.com</a>
                </p>
                <p>
                    <i class="fab fa-instagram"></i> 📸 **Instagram:** <a href="https://instagram.com/kamakshiii_singh" target="_blank" rel="noopener noreferrer">@kamakshiii_singh</a>
                </p>
                <p>
                    <i class="fab fa-snapchat-ghost"></i> 👻 **Snapchat:** <a href="https://snapchat.com/add/kaaaaaaashu" target="_blank" rel="noopener noreferrer">@kaaaaaaashu</a>
                </p>
                <p>
                    <i class="fab fa-linkedin"></i> 💼 **LinkedIn:** <a href="https://linkedin.com/in/kamakshi-singh-40685a395" target="_blank" rel="noopener noreferrer">linkedin.com/in/kamakshi-singh-40685a395</a>
                </p>
            </div>
        </div>
    </section>

    <footer>
        <div class="socials">
            <a href="https://linkedin.com/in/kamakshi-singh-40685a395" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn"><i class="fab fa-linkedin fa-2x"></i></a>
            <a href="https://instagram.com/kamakshiii_singh" target="_blank" rel="noopener noreferrer" aria-label="Instagram"><i class="fab fa-instagram fa-2x"></i></a>
            <a href="https://snapchat.com/add/kaaaaaaashu" target="_blank" rel="noopener noreferrer" aria-label="Snapchat"><i class="fab fa-snapchat-ghost fa-2x"></i></a>
        </div>
        <p>&copy; 2025 Portfolio. All rights reserved.</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const form = document.getElementById('contact-form');
            const formStatus = document.getElementById('form-status');

            if (form) {
                form.addEventListener('submit', async (e) => {
                    e.preventDefault(); 
                    
                    formStatus.textContent = 'Sending message...';
                    formStatus.style.color = 'var(--color-primary)';
                    
                    const formData = new FormData(form);
                    
                    // The following logic will only work if you replace "YOUR_FORMSPREE_ENDPOINT"
                    // with an actual endpoint from a form service.
                    
                    try {
                        const response = await fetch(form.action, {
                            method: 'POST',
                            body: formData,
                            headers: {
                                'Accept': 'application/json'
                            }
                        });

                        if (response.ok) {
                            formStatus.textContent = 'Thank you! Your message has been sent successfully.';
                            formStatus.style.color = 'green';
                            form.reset(); 
                        } else {
                            // Handle service-specific errors
                            formStatus.textContent = 'Oops! There was an issue sending your message. Check the endpoint URL.';
                            formStatus.style.color = 'red';
                        }
                    } catch (error) {
                        // Handle network or fetch errors
                        formStatus.textContent = 'Error: Could not connect to the form service.';
                        formStatus.style.color = 'red';
                    }
                });
            }
        });
    </script>
</body>
</html>
