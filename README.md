# Ex01 Portfolio
## Date: 27-10-26

## AIM
To create a Portfolio using HTML and CSS.

## ALGORITHM
### STEP 1
Create an HTML file (index.html)

### STEP 2
Create a CSS file (style.css)

### STEP 3
Include a navigation bar with links to different sections.

### STEP 4
Add structured sections for introduction, about, projects, and contact details.

### STEP 5
Define global styles for fonts, colors, and layout.

### STEP 6
Style the header, navigation bar, and sections.

### STEP 7
Use Flexbox or CSS Grid for layout design.

### STEP 8
Add hover effects and transitions for interactivity.

### STEP 9
Add Images and Media.

### STEP 10
Use optimized images for a professional look.

### STEP 11
Open the HTML file in a browser to check layout and functionality.

### STEP 12
Fix styling issues and refine content placement.

### STEP 13
Deploy the Portfolio.

### STEP 14
Upload to GitHub Pages for free hosting.

## PROGRAM
<h1>index.html</h1>

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Bhavitra | Portfolio</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>

  <!-- ===== Header ===== -->
  <header>
    <div class="logo">Bhavitra<span>.</span></div>
    <nav>
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <!-- ===== Hero Section ===== -->
  <section id="home" class="hero">
    <div class="hero-content">
      <h1>Hello, I'm <span>Bhavitra Bhaskaran</span></h1>
      <p>A passionate <strong>Computer Science Student</strong> exploring Web Development & Design.</p>
      <button onclick="scrollToSection('contact')">Let’s Connect 🚀</button>
    </div>
  </section>

  <!-- ===== About Section ===== -->
  <section id="about" class="section fade-in">
    <h2>About Me</h2>
     <div class="about-container">
    
   
    <img src="image/photo.jpeg" alt="Bhavitra Photo" class="profile-pic" />

    <p>
     I’m Bhavitra Bhaskaran, a Computer Science and Engineering student at Saveetha Engineering College.
I’m passionate about web development, UI design, and problem-solving.
I enjoy exploring new technologies, building creative projects, and constantly improving my skills in HTML, CSS, JavaScript, and React.
My goal is to become a skilled frontend developer who creates beautiful and user-friendly web experiences.
    </p>
  </div>
  </section>

  <!-- ===== Skills Section ===== -->
  <section id="skills" class="section fade-in">
    <h2>My Skills</h2>
    <div class="skills-container">
      <div class="skill-card">HTML5</div>
      <div class="skill-card">CSS3</div>
      <div class="skill-card">JavaScript</div>
      <div class="skill-card">React (Learning)</div>
      <div class="skill-card">Git & GitHub</div>
    </div>
  </section>


    <!-- ===== Experience Section ===== -->
  <section id="experience" class="section fade-in">
    <h2>Experience</h2>
    <div class="experience-container">

      <div class="experience-card">
        <h3>Web Development Intern</h3>
      
        <p>
          Designed responsive websites using <b>HTML</b>, <b>CSS</b>, and <b>JavaScript</b>.
          Collaborated with a team to create interactive UI components and improve user experience.
        </p>
      </div>

      <div class="experience-card">
        <h3>Frontend Project</h3>
        <h4>Personal Portfolio Website | 2025</h4>
        <p>
          Built a personal portfolio from scratch using modern web technologies.
          Implemented animations, responsive design, and interactive contact forms.
        </p>
      </div>

      <div class="experience-card">
        <h3>Event Participant</h3>
        <h4>Frontend Fusion | Saveetha Engineering College</h4>
        <p>
          Participated in a web design event focused on creativity and frontend innovation.
          Showcased skills in layout design, animations, and user interaction.
        </p>
      </div>

    </div>
  </section>


  <!-- ===== Contact Section ===== -->
  <section id="contact" class="section fade-in">
    <h2>Contact Me</h2>
    <form id="contactForm">
      <input type="text" id="name" placeholder="Your Name" required />
      <input type="email" id="email" placeholder="Your Email" required />
      <textarea id="message" placeholder="Your Message" required></textarea>
      <button type="submit">Send Message</button>
    </form>
    <p id="formMessage"></p>
  </section>

  <!-- ===== Footer ===== -->
  <footer>
    <p>© 2025 Bhavitra Bhaskaran | Designed with 💚 & Code</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>
```

<h1>script.js</h1>


```
// Smooth scroll to section
function scrollToSection(id) {
  document.getElementById(id).scrollIntoView({ behavior: "smooth" });
}

// Contact form functionality
const form = document.getElementById("contactForm");
const message = document.getElementById("formMessage");

form.addEventListener("submit", (e) => {
  e.preventDefault();
  const name = document.getElementById("name").value;
  message.textContent = `Thank you, ${name}! Your message has been sent successfully 🌟`;
  message.style.color = "#2e7d32";
  form.reset();
});

// Fade-in animation on scroll
const faders = document.querySelectorAll(".fade-in");
window.addEventListener("scroll", () => {
  faders.forEach((section) => {
    const sectionTop = section.getBoundingClientRect().top;
    const triggerPoint = window.innerHeight * 0.85;
    if (sectionTop < triggerPoint) {
      section.classList.add("visible");
    }
  });
});
```

<h1>style.css</h1>


```
/* ===== Global Styles ===== */
* {
  box-sizing: border-box;
  scroll-behavior: smooth;
}

body {
  margin: 0;
  font-family: "Poppins", sans-serif;
  color: #333;
  background: linear-gradient(135deg, #e0f7fa, #f1f8e9);
}

/* ===== Header ===== */
header {
  position: sticky;
  top: 0;
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 40px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  z-index: 100;
}

.logo {
  font-size: 1.6em;
  font-weight: 700;
  color: #2e7d32;
}

.logo span {
  color: #43a047;
}

nav ul {
  display: flex;
  list-style: none;
  gap: 20px;
  margin: 0;
}

nav a {
  text-decoration: none;
  color: #333;
  font-weight: 600;
  transition: color 0.3s;
}

nav a:hover {
  color: #43a047;
}

/* ===== Hero Section ===== */
.hero {
  height: 90vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #81c784, #4caf50);
  color: white;
  text-align: center;
}

.hero-content h1 {
  font-size: 2.5em;
}

.hero-content span {
  color: #fff59d;
}

.hero-content p {
  font-size: 1.1em;
  margin: 15px 0;
}

.hero-content button {
  background: white;
  color: #388e3c;
  border: none;
  padding: 12px 25px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
  transition: 0.3s;
}

.hero-content button:hover {
  background: #f1f8e9;
  transform: scale(1.05);
}

/* ===== Section Styles ===== */
.section {
  padding: 80px 20px;
  text-align: center;
  background: white;
  margin: 40px auto;
  border-radius: 15px;
  width: 90%;
  max-width: 1000px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}

.section h2 {
  color: #388e3c;
  font-size: 2em;
  margin-bottom: 20px;
}

.section p {
  font-size: 1.1em;
  max-width: 700px;
  margin: auto;
  color: #555;
}

/* ===== About Section with Image ===== */
.about-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 25px;
  text-align: center;
  margin-top: 20px;
}

.profile-pic {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  object-fit: cover;
  border: 5px solid #4CAF50;
  box-shadow: 0 0 25px rgba(76, 175, 80, 0.6);
  transition: transform 0.4s ease, box-shadow 0.4s ease;
  animation: popIn 1s ease-out forwards;
  opacity: 0;
}

.profile-pic:hover {
  transform: scale(1.1);
  box-shadow: 0 0 40px rgba(76, 175, 80, 0.8);
}

/* Smooth fade-in effect */
@keyframes popIn {
  0% {
    transform: scale(0.8);
    opacity: 0;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}


/* ===== Skills ===== */
.skills-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
  margin-top: 30px;
}

.skill-card {
  background: linear-gradient(135deg, #a5d6a7, #66bb6a);
  color: white;
  padding: 20px 30px;
  border-radius: 12px;
  font-weight: bold;
  transition: transform 0.3s, box-shadow 0.3s;
}

.skill-card:hover {
  transform: scale(1.1);
  box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3);
}

/* ===== Experience Section ===== */
.experience-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(270px, 1fr));
  gap: 20px;
  margin-top: 30px;
}

.experience-card {
  background: linear-gradient(135deg, #ffffff, #e8f5e9);
  border-radius: 16px;
  padding: 20px;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.15);
  transition: transform 0.4s ease, box-shadow 0.4s ease;
  border-left: 6px solid #4CAF50;
}

.experience-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4);
}

.experience-card h3 {
  margin-bottom: 8px;
  color: #2e7d32;
  font-size: 1.3rem;
}

.experience-card h4 {
  font-size: 1rem;
  color: #555;
  margin-bottom: 10px;
}

.experience-card p {
  color: #333;
  line-height: 1.6;
}


/* ===== Contact Form ===== */
form {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  max-width: 400px;
  margin: 0 auto;
}

input, textarea {
  width: 100%;
  padding: 10px;
  border-radius: 8px;
  border: 1px solid #ccc;
  font-size: 1em;
}

button {
  background-color: #43a047;
  color: white;
  border: none;
  padding: 12px 20px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 1em;
  font-weight: 600;
  transition: 0.3s;
}

button:hover {
  background-color: #2e7d32;
  transform: scale(1.05);
}

/* ===== Footer ===== */
footer {
  background: #2e7d32;
  color: white;
  text-align: center;
  padding: 15px;
  margin-top: 40px;
  font-size: 0.9em;
}

/* ===== Animations ===== */
.fade-in {
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 0.8s ease, transform 0.8s ease;
}

.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}


.social-links {
  display: flex;
  gap: 20px;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.05);
  color: var(--text-dim);
  font-size: 1.5rem;
  transition: var(--transition);
  border: 1px solid rgba(255, 255, 255, 0.1);
  text-decoration: none;
}

.social-link:hover {
  background: var(--neon-red);
  color: #000;
  transform: translateY(-8px);
  box-shadow: 0 10px 25px rgba(255, 0, 60, 0.4);
  border-color: var(--neon-red);
}
```


## OUTPUT
![alt text](<Screenshot 2026-10-27 124735.png>)

![alt text](<Screenshot 2026-10-27 124800.png>)

![alt text](<Screenshot 2026-10-27 124825.png>)

![alt text](<Screenshot 2026-10-27 124836.png>)

![alt text](<Screenshot 2026-10-27 124847.png>)

## RESULT
The program for creating Portfolio using HTML and CSS is executed successfully.
