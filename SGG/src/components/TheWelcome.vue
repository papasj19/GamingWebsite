<template>
  <div class="studio-gato-galactic">
    <!-- HEADER -->
    <header class="site-header">
      <nav class="navbar">
        <a href="#" class="logo">Studio Gato Galactico</a>
        <ul class="nav-links">
          <li><a href="#home">Home</a></li>
          <li><a href="#games">Games</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </header>

    <!-- HERO SECTION -->
    <section id="home" class="hero">
      <div class="hero-overlay"></div>
      <div class="hero-content">
        <h1>Indie Games from the Stars</h1>
        <p>Where cosmic creativity meets epic gameplay. Inspired by classics like Halo.</p>
        <button class="cta-button" @click="exploreGames">Explore Our Games</button>
      </div>
    </section>

    <!-- FEATURED GAMES SECTION -->
    <section id="games" class="games-section">
      <h2 class="section-title">Our Games</h2>
      <p class="section-subtitle">
        Check out our latest indie adventures, born from our love for epic universes
        like Halo and beyond.
      </p>
      <div class="games-grid">
        <div v-for="(game, index) in games" :key="index" class="game-card">
          <img :src="game.image" :alt="game.title" class="game-image" />
          <h3 class="game-title">{{ game.title }}</h3>
          <p class="game-description">{{ game.description }}</p>
        </div>
      </div>
    </section>

    <!-- ABOUT US SECTION -->
    <section id="about" class="about-section">
      <div class="about-content">
        <h2 class="section-title">About Studio Gato Galactic</h2>
        <p>
          Studio Gato Galactic is a passionate team of indie developers on a mission to
          craft immersive, story-driven games. Our love for the Halo franchise fuels our
          fascination with epic worlds, cinematic action, and memorable characters.
        </p>
        <p>
          Whether it’s forging new galactic realms or bringing dynamic co-op experiences to life,
          our focus is on delivering innovative, heartfelt gameplay experiences.
        </p>
      </div>
      <img
          src="https://images.unsplash.com/photo-1539906605622-ecfcedf1a3ba?auto=format&q=80"
          alt="About Us"
          class="about-image"
      />
    </section>

    <!-- CONTACT SECTION -->
    <section id="contact" class="contact-section">
      <h2 class="section-title">Stay In Touch</h2>
      <p>Sign up for our newsletter to get the latest updates on our upcoming games and events.</p>
      <form class="contact-form" @submit.prevent="subscribe">
        <input
            type="email"
            v-model="email"
            placeholder="Enter your email"
            required
        />
        <button type="submit" class="cta-button">Subscribe</button>
      </form>
    </section>

    <!-- FOOTER -->
    <footer class="site-footer">
      <p>
        © {{ new Date().getFullYear() }} Studio Gato Galactic. All rights reserved.
        <br>
        *Halo is a registered trademark of Microsoft. Studio Gato Galactic is not associated with or endorsed by Microsoft.
      </p>
    </footer>
  </div>
</template>

<script>
export default {
  name: "StudioGatoGalacticLanding",
  data() {
    return {
      games: [
        {
          title: "Cosmic Claws",
          description: "A feline adventure across cosmic frontiers, filled with platforming, puzzles, and starry surprises.",
          image:
              "https://images.unsplash.com/photo-1590774605467-290db979b348?auto=format&q=80"
        },
        {
          title: "Starbound Tactics",
          description: "Real-time strategy meets cosmic warfare in this fast-paced, interstellar RTS saga.",
          image:
              "https://images.unsplash.com/photo-1576495199013-5c564c48f5bc?auto=format&q=80"
        },
        {
          title: "Nebula Flight",
          description: "Pilot your ship through galactic dogfights and unravel cosmic mysteries in this indie space sim.",
          image:
              "https://images.unsplash.com/photo-1553860587-2b9c6154f6b3?auto=format&q=80"
        },
        {
          title: "Halo-Inspired Marathon",
          description:
              "Fast-paced FPS action that pays homage to the intense battles and arena-like gameplay we love in Halo.",
          image:
              "https://images.unsplash.com/photo-1606059726152-31d7d5eb3294?auto=format&q=80"
        }
      ],
      email: ""
    };
  },
  methods: {
    exploreGames() {
      // Scroll to the games section
      const el = document.getElementById("games");
      el && el.scrollIntoView({ behavior: "smooth" });
    },
    subscribe() {
      // Handle newsletter signup logic here
      alert(`Thanks for subscribing, ${this.email}!`);
      this.email = "";
    }
  }
};
</script>

<style scoped>
/* BASIC RESET */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* COLORS & FONTS */
:root {
  --bg-color: #121212;
  --primary-color: #00ffc8;
  --secondary-color: #ffffff;
  --accent-color: #00ffc8; /* neon green/teal accent */
  --text-color: #cccccc;
  --heading-color: #ffffff;
  --font-family: 'Roboto', sans-serif;
}

/* OVERALL PAGE WRAPPER */
.studio-gato-galactic {
  font-family: var(--font-family);
  background-color: var(--bg-color);
  color: var(--text-color);
}

/* HEADER */
.site-header {
  background-color: #1a1a1a;
  padding: 1rem 2rem;
  position: sticky;
  top: 0;
  z-index: 999;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  text-decoration: none;
  color: var(--accent-color);
  font-size: 1.5rem;
  font-weight: bold;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 1.5rem;
}

.nav-links li a {
  color: var(--secondary-color);
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.nav-links li a:hover {
  color: var(--accent-color);
}

/* HERO SECTION */
.hero {
  position: relative;
  height: 70vh;
  background: url('https://images.unsplash.com/photo-1603481543728-3f92166c4571?auto=format&q=80') no-repeat center/cover;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.hero-overlay {
  position: absolute;
  inset: 0;
  background-color: rgba(0, 0, 0, 0.5);
}

.hero-content {
  position: relative;
  max-width: 700px;
  padding: 2rem;
  z-index: 1;
}

.hero-content h1 {
  font-size: 2.5rem;
  color: var(--secondary-color);
  margin-bottom: 1rem;
}

.hero-content p {
  font-size: 1.2rem;
  margin-bottom: 2rem;
}

/* CTA BUTTON */
.cta-button {
  background-color: var(--accent-color);
  color: #000;
  border: none;
  padding: 0.75rem 1.5rem;
  font-size: 1rem;
  border-radius: 4px;
  cursor: pointer;
  font-weight: 600;
  transition: background 0.3s ease;
}

.cta-button:hover {
  background-color: #00eab5;
}

/* SECTION TITLES */
.section-title {
  text-align: center;
  color: var(--heading-color);
  font-size: 2rem;
  margin-bottom: 1rem;
}

.section-subtitle {
  text-align: center;
  color: #999;
  margin-bottom: 2rem;
  font-size: 1rem;
  max-width: 600px;
  margin: 1rem auto 2rem;
}

/* GAMES SECTION */
.games-section {
  padding: 2rem;
}

.games-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.game-card {
  background-color: #1e1e1e;
  border-radius: 8px;
  overflow: hidden;
  text-align: center;
  padding: 1rem;
  box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}

.game-image {
  width: 100%;
  height: 160px;
  object-fit: cover;
  margin-bottom: 1rem;
  border-radius: 8px;
}

.game-title {
  font-size: 1.2rem;
  color: var(--secondary-color);
  margin-bottom: 0.5rem;
}

.game-description {
  font-size: 1rem;
  color: #cccccc;
}

/* ABOUT SECTION */
.about-section {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 2rem;
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.about-content {
  flex: 1 1 400px;
}

.about-image {
  flex: 1 1 400px;
  width: 100%;
  max-width: 500px;
  border-radius: 8px;
  object-fit: cover;
}

/* CONTACT SECTION */
.contact-section {
  text-align: center;
  padding: 2rem;
}

.contact-form {
  margin-top: 1rem;
}

.contact-form input[type="email"] {
  padding: 0.5rem;
  font-size: 1rem;
  border: none;
  border-radius: 4px;
  margin-right: 0.5rem;
  width: 250px;
}

.contact-form input[type="email"]:focus {
  outline: 2px solid var(--accent-color);
}

/* FOOTER */
.site-footer {
  background-color: #1a1a1a;
  padding: 1rem;
  text-align: center;
  color: #777;
  font-size: 0.9rem;
  margin-top: 2rem;
  box-shadow: 0 -2px 8px rgba(0,0,0,0.2);
}
</style>