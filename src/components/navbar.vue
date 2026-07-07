<template>
  <nav class="navbar">
    <div class="navbar-logo">
      <router-link to="/">MiLogo</router-link>
    </div>

    <button class="navbar-toggle" @click="menuAbierto = !menuAbierto">
      ☰
    </button>

    <ul class="navbar-links" :class="{ activo: menuAbierto }">
      <li>
        <router-link to="/" @click="menuAbierto = false">Inicio</router-link>
      </li>
      <li>
        <router-link to="/about" @click="menuAbierto = false">Nosotros</router-link>
      </li>
      <li>
        <router-link to="/contact" @click="menuAbierto = false">Contacto</router-link>
      </li>
    </ul>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const menuAbierto = ref(false)
</script>

<style scoped>
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 2rem;
  background-color: #2c3e50;
  color: white;
}

.navbar-logo a {
  color: white;
  font-weight: bold;
  font-size: 1.3rem;
  text-decoration: none;
}

.navbar-links {
  display: flex;
  list-style: none;
  gap: 1.5rem;
  margin: 0;
  padding: 0;
}

.navbar-links a {
  color: white;
  text-decoration: none;
  transition: color 0.2s;
}

.navbar-links a:hover,
.navbar-links a.router-link-active {
  color: #42b883;
}

.navbar-toggle {
  display: none;
  background: none;
  border: none;
  color: white;
  font-size: 1.5rem;
  cursor: pointer;
}

/* Responsive */
@media (max-width: 768px) {
  .navbar-toggle {
    display: block;
  }

  .navbar-links {
    position: absolute;
    top: 60px;
    left: 0;
    right: 0;
    flex-direction: column;
    background-color: #2c3e50;
    display: none;
    padding: 1rem 2rem;
  }

  .navbar-links.activo {
    display: flex;
  }
}
</style>