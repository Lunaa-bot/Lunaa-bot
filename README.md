<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>E-Learning Vault</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <!-- Video Background -->
  <div class="video-container">
    <video autoplay muted loop playsinline>
      <source src="/video.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
  </div>

  <!-- Main Content -->
  <div class="main-content">
    <!-- Navigation Bar -->
    <nav class="navigation">
      <ul>
        <li><button onclick="showSection('home')">Home</button></li>
        <li><button onclick="showSection('about')">About</button></li>
        <li><button onclick="showSection('books')">Books</button></li>
        <li><button onclick="showSection('contact')">Contact</button></li>
      </ul>
    </nav>

    <!-- Sections -->
    <section id="home" class="content-section active">
      <h1>Welcome to E-Learning Vault</h1>
      <p>Your ultimate platform for online education and resources.</p>
    </section>

    <section id="about" class="content-section hidden">
      <h1>About Us</h1>
      <p>At E-Learning Vault, we empower learners with high-quality resources to fuel their academic and professional growth.</p>
    </section>

    <section id="books" class="content-section hidden">
      <h1>Our Books</h1>
      <div class="book-grid">
        <div class="book-item">
          <img src="https://i.ibb.co/gS7Bzsv/images-2.jpg" alt="English Dictionary">
          <h3>English Proficiency</h3>
          <p>Author: Merriam-Webster</p>
        </div>
        <div class="book-item">
          <img src="https://i.ibb.co/MZbhcRf/images-1.jpg" alt="Ancient Rome">
          <h3>History of Ancient Rome</h3>
          <p>Author: Mary Beard</p>
        </div>
        <div class="book-item">
          <img src="https://i.ibb.co/Bqy9BxD/images.jpg" alt="Teaching and the Brain">
          <h3>Teaching & The Brain</h3>
          <p>Author: Zaretta Hammond</p>
        </div>
      </div>
    </section>

    <section id="contact" class="content-section hidden">
      <h1>Contact Us</h1>
      <form>
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required>
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>
        <label for="message">Message:</label>
        <textarea id="message" name="message" rows="5"></textarea>
        <button type="submit">Send</button>
      </form>
    </section>
  </div>

  <script src="script.js"></script>
</body>
</html>


body {
    
}/* General Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Video Background */
.video-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}

.video-container video {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Main Content */
.main-content {
  position: relative;
  width: 100%;
  height: 100%;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

/* Navigation */
.navigation {
  position: absolute;
  top: 10px;
  display: flex;
  justify-content: center;
  width: 100%;
  background: rgba(0, 0, 0, 0.7);
  padding: 10px 0;
  z-index: 1;
}

.navigation ul {
  list-style: none;
  display: flex;
  gap: 20px;
}

.navigation ul li button {
  background: none;
  color: white;
  border: 1px solid white;
  padding: 10px 15px;
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.3s;
}

.navigation ul li button:hover {
  background-color: #ffcb6b;
  color: black;
}

/* Content Sections */
.content-section {
  text-align: center;
  padding: 50px 20px;
  display: none;
  background: rgba(0, 0, 0, 0.6); /* Transparent background */
  border-radius: 10px;
  width: 80%;
  max-width: 1200px;
}

.content-section.active {
  display: block;
}

/* Book Grid */
.book-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
}

.book-item {
  text-align: center;
  max-width: 200px;
}

.book-item img {
  width: 100%;
  border-radius: 10px;
}

function showSection(sectionId) {
  const sections = document.querySelectorAll('.content-section');
  sections.forEach((section) => {
    section.classList.remove('active');
  });

  const activeSection = document.getElementById(sectionId);
  activeSection.classList.add('active');
}
