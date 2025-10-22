<script setup lang="ts">
import { ref } from "vue";
import Button from "../Button/Button.vue";
import Logo from "../Logo/Logo.vue";

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};
</script>

<template>
  <div class="navbar-container">
    <div class="navbar">
      <Logo />

      <div class="nav-links desktop-nav">
        <p>Home</p>
        <p>Ranking</p>
        <p>Guildas</p>
        <p>Torneios</p>
        <p>Ginásios</p>
        <p>TCG</p>
      </div>

      <div class="nav-buttons desktop-nav">
        <Button>Login</Button>
        <Button :isFocus="true">Registrar-se</Button>
      </div>

      <button class="menu-toggle" @click="toggleMenu" aria-label="Menu">
        <span :class="{ open: isMenuOpen }"></span>
        <span :class="{ open: isMenuOpen }"></span>
        <span :class="{ open: isMenuOpen }"></span>
      </button>
    </div>

    <div class="mobile-dropdown" :class="{ open: isMenuOpen }">
      <div class="mobile-nav-links">
        <p @click="toggleMenu">Home</p>
        <p @click="toggleMenu">Ranking</p>
        <p @click="toggleMenu">Guildas</p>
        <p @click="toggleMenu">Torneios</p>
        <p @click="toggleMenu">Ginásios</p>
        <p @click="toggleMenu">TCG</p>
      </div>
      <div class="mobile-nav-buttons">
        <Button>Login</Button>
        <Button>Registrar-se</Button>
      </div>
    </div>
  </div>
</template>

<style>
@keyframes expandFromCenter {
  0% {
    transform: scaleX(0);
    opacity: 0;
  }
  100% {
    transform: scaleX(1);
    opacity: 1;
  }
}

@keyframes slideDown {
  0% {
    opacity: 0;
    transform: translateY(-20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.navbar-container {
  position: fixed;
  top: 16px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 1000;
  width: 90%;
  max-width: 1360px;
}

.navbar {
  display: flex;
  flex-direction: row;
  align-items: center;
  background: var(--black);
  height: auto;
  padding: 8px clamp(20px, 5vw, 60px);
  margin: 0;
  gap: 20px;
  border-radius: 8px;
  border: 2px solid rgba(237, 235, 221, 0.15);
  backdrop-filter: blur(10px);
  animation: expandFromCenter 0.6s cubic-bezier(0.34, 1.56, 0.64, 1) forwards;
  transform-origin: center;
}

.navbar h1 {
  margin: 0;
  font-size: clamp(20px, 3vw, 28px);
  flex-shrink: 0;
  color: var(--white);
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.nav-links {
  display: flex;
  gap: 25px;
  padding: 10px 35px;
  margin: 0 auto;
  align-items: center;
}

.nav-links p {
  margin: 0;
  cursor: pointer;
  font-size: 13px;
  white-space: nowrap;
  color: var(--white);
  transition: all 0.3s ease;
  position: relative;
}

.nav-links p::after {
  content: "";
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 1px;
  background: var(--white);
  transition: width 0.3s ease;
}

.nav-links p:hover {
  transform: translateY(-2px);
  text-shadow: 0 2px 8px rgba(237, 235, 221, 0.5);
}

.nav-links p:hover::after {
  width: 100%;
}

.nav-buttons {
  display: flex;
  gap: 15px;
  margin: 0;
  align-items: center;
  flex-shrink: 0;
}

.menu-toggle {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 8px;
  margin-left: auto;
}

.menu-toggle span {
  display: block;
  width: 25px;
  height: 3px;
  background: var(--white);
  border-radius: 2px;
  transition: all 0.3s ease;
}

.menu-toggle span.open:nth-child(1) {
  transform: rotate(45deg) translate(7px, 7px);
}

.menu-toggle span.open:nth-child(2) {
  opacity: 0;
}

.menu-toggle span.open:nth-child(3) {
  transform: rotate(-45deg) translate(7px, -7px);
}

.mobile-dropdown {
  background: var(--black);
  border-radius: 12px;
  margin-top: 12px;
  padding: 20px;
  box-shadow:
    0 8px 32px rgba(0, 0, 0, 0.4),
    inset 0 1px 0 rgba(237, 235, 221, 0.1);
  border: 2px solid rgba(237, 235, 221, 0.15);
  backdrop-filter: blur(10px);

  max-height: 0;
  overflow: hidden;
  opacity: 0;
  transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
  pointer-events: none;
}

.mobile-dropdown.open {
  max-height: 500px;
  opacity: 1;
  pointer-events: all;
  animation: slideDown 0.4s ease-out;
}

.mobile-nav-links {
  display: flex;
  flex-direction: column;
  gap: 15px;
  margin-bottom: 20px;
}

.mobile-nav-links p {
  margin: 0;
  cursor: pointer;
  font-size: 16px;
  color: var(--white);
  padding: 10px;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.mobile-nav-links p:hover {
  background: rgba(237, 235, 221, 0.1);
  transform: translateX(5px);
}

.mobile-nav-buttons {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.mobile-nav-buttons button {
  width: 100%;
}

@media (max-width: 1224px) {
  .desktop-nav {
    display: none !important;
  }

  .menu-toggle {
    display: flex;
  }

  .navbar {
    padding: 15px 20px;
  }

  .navbar-container {
    width: 95%;
  }
}

@media (max-width: 480px) {
  .navbar h1 {
    font-size: 20px;
  }

  .navbar-container {
    top: 12px;
  }
}
</style>
