<script setup>
const props = defineProps({
  size: {
    type: String,
    default: 'medium' // small, medium, large
  }
});

const sizes = {
  small: { fontSize: '18px' },
  medium: { fontSize: '28px' },
  large: { fontSize: '42px' }
};

const currentSize = sizes[props.size] || sizes.medium;
</script>

<template>
  <div class="logo" :style="{ fontSize: currentSize.fontSize }">
    <!-- Nuvens brancas atrás do texto -->
    <div class="clouds-bg">
      <svg class="cloud cloud-left" viewBox="0 0 60 30" fill="none">
        <ellipse cx="15" cy="18" rx="8" ry="8" fill="#ffffff"/>
        <ellipse cx="25" cy="15" rx="12" ry="10" fill="#ffffff"/>
        <ellipse cx="38" cy="16" rx="10" ry="9" fill="#ffffff"/>
        <ellipse cx="48" cy="19" rx="7" ry="7" fill="#ffffff"/>
        <rect x="15" y="18" width="33" height="4" fill="#ffffff"/>
      </svg>
      
      <svg class="cloud cloud-right" viewBox="0 0 55 28" fill="none">
        <ellipse cx="12" cy="16" rx="7" ry="7" fill="#ffffff"/>
        <ellipse cx="22" cy="13" rx="10" ry="9" fill="#ffffff"/>
        <ellipse cx="33" cy="14" rx="9" ry="8" fill="#ffffff"/>
        <ellipse cx="42" cy="17" rx="6" ry="6" fill="#ffffff"/>
        <rect x="12" y="16" width="30" height="4" fill="#ffffff"/>
      </svg>
    </div>
    
    <h1 class="logo-text">
      <span class="letter">L</span>
      <span class="letter">a</span>
      <span class="letter">n</span>
      <span class="letter">d</span>
      <span class="letter highlight">l</span>
      <span class="letter highlight">o</span>
      <span class="letter highlight">s</span>
    </h1>
  </div>
</template>

<style>
@font-face {
  font-family: "minecraftia";
  src: url("/fonts/Minecraftia-Regular.ttf") format("truetype");
  font-weight: normal;
  font-style: normal;
}

.logo {
  display: inline-flex;
  align-items: center;
  position: relative;
  user-select: none;
  cursor: pointer;
  padding: 4px 0;
}

/* Nuvens de fundo */
.clouds-bg {
  position: absolute;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 0;
}

.cloud {
  position: absolute;
  opacity: 0.45;
  pointer-events: none;
}

.cloud-left {
  width: 45px;
  height: auto;
  top: 10%;
  left: -15px;
  animation: driftLeft 8s ease-in-out infinite;
}

.cloud-right {
  width: 40px;
  height: auto;
  bottom: 10%;
  right: -20px;
  animation: driftRight 10s ease-in-out infinite;
}

@keyframes driftLeft {
  0%, 100% {
    transform: translateX(0) translateY(0);
  }
  50% {
    transform: translateX(-8px) translateY(-3px);
  }
}

@keyframes driftRight {
  0%, 100% {
    transform: translateX(0) translateY(0);
  }
  50% {
    transform: translateX(10px) translateY(3px);
  }
}

.logo-text {
  margin: 0;
  font-family: "minecraftia", monospace;
  color: var(--white);
  text-shadow: 
    2px 2px 0px var(--red),
    3px 3px 0px rgba(0, 0, 0, 0.5);
  letter-spacing: 3px;
  position: relative;
  display: flex;
  z-index: 1;
}

.logo-text .letter {
  display: inline-block;
  transition: all 0.3s ease;
}

/* Últimas 3 letras em destaque */
.logo-text .highlight {
  color: var(--red);
  text-shadow: 
    2px 2px 0px var(--dark-red),
    3px 3px 0px rgba(0, 0, 0, 0.5),
    0 0 12px var(--red)
}

/* Hover suave */
.logo:hover .logo-text {
  text-shadow: 
    2px 2px 0px var(--red),
    3px 3px 0px rgba(0, 0, 0, 0.5),
    0 0 15px var(--red)
}

.logo:hover .cloud {
  opacity: 0.45;
  animation-duration: 4s;
}

/* Responsivo */
@media (max-width: 768px) {
  .logo-text {
    letter-spacing: 2px;
  }
  
  .cloud-left {
    width: 35px;
  }
  
  .cloud-right {
    width: 30px;
  }
}
</style>
