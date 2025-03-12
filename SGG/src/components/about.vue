<script setup>

</script>

<script>
  export default{
    name: "About",
    data() {
      return {
        info: [
          {
            title: "About Us",
            image: "/icon.png"
          }
        ]
      }
    }


  }

</script>

<template>

  <!-- ABOUT US SECTION -->
  <section id="about" class="about-section">
    <div class="about-content">
      <h2 class="section-title">About Studio Gato Galactico</h2>
      <p>
        Studio Gato Galactico is a passionate team of indie developers on a mission to
        craft immersive, story-driven games. Our love for the Halo franchise fuels our
        fascination with epic worlds, cinematic action, and memorable characters.
      </p>
      <p>
        Whether it’s forging new galactic realms or bringing dynamic co-op experiences to life,
        our focus is on delivering innovative, heartfelt gameplay experiences.
      </p>
    </div>
    <img
        :src=  info[0].image
        alt="About Us"
        class="about-image"
    />
  </section>

</template>

<style scoped>


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
  border-radius: 8px;
  object-fit: contain;
  height: 40vh;
}

</style>