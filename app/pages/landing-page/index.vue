<script setup lang="ts">
import Header from "~/components/Header/Header.vue";
</script>
<template>
  <div class="wrapper">
    <Header />
    <div class="Img">
      <h1>Sua história começa aqui</h1>
    </div>
    <div class="Corpo2">
      <div class="Quadrado1">
        <h1>De novato a Lenda!</h1>
        <p>
          Encare desafios, <strong>ganhe prêmios</strong> e conquiste seu lugar
          no topo do <strong>Ranking</strong> Global de Cobblemon.
        </p>
        <p class="ComeceJa">Comece já</p>
        <img src="/images/placeholder.gif" />
      </div>
    </div>
  </div>
</template>
<style>
@font-face {
  font-family: "Minercraftory";
  src: url("/fonts/Minercraftory.ttf") format("truetype");
  font-weight: normal;
  font-style: normal;
}

strong {
  color: black;
}

body {
  min-height: 100vh;
  overflow-x: hidden;
  background: linear-gradient(135deg, #000000 45%, #521a14 55%);
  margin: 0;
  padding: 0;
}

.wrapper {
  padding: 0px 32px;
}

.ComeceJa {
  position: absolute;
  border: solid black 10px;
  background-color: #000000;
  border-radius: 10px;
  width: 200px;
  padding: 15px 30px;
  text-align: center;
  font-size: 16px;
  cursor: pointer;
  bottom: 100px;
  left: 120px;
}

.Corpo2 {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: calc(100vh - 700px);
  overflow-x: hidden;
}

.Quadrado1 {
  display: flex;
  flex-direction: column;
  background-color: #c9c9c9;
  height: 500px;
  width: 1900px;
  max-width: 3000px;
  border-radius: 15px;
  flex-shrink: 0;
  position: relative;
  padding: 20px;
  box-sizing: border-box;
}

.Quadrado1 img {
  position: absolute;
  border: solid black 10px;
  background-color: black;
  bottom: 130px;
  right: 20px;
  width: 300px;
  height: 350px;
}

p,
h1 {
  font-family: "minecraftia";
  color: white;
}

.Img {
  position: relative;
  margin: 0;
  height: 700px;
  width: 100%;
  padding: 20px;
  box-sizing: border-box;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}

.Img::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: url("/images/lg-bg.png");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  filter: blur(5px);
  z-index: 0;
}

.Img h1 {
  color: var(--red);
  margin: 0;
  text-align: center;
  font-size: 3rem;
  position: relative;
  z-index: 1;
  text-shadow:
    3px 3px 0px black,
    4px 4px 0px rgba(0, 0, 0, 0.5);
}
</style>
