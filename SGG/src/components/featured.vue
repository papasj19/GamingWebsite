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
      ]}
    }
}

</script>

<template>

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

</template>

<style scoped>


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

</style>