<template>
  <div class="Navbar">
    <h1>Landlos</h1>

    <div class="nav-links">
      <p>Home</p>
      <p>Ranking</p>
      <p>Guildas</p>
      <p>Torneios</p>
      <p>Ginásios</p>
      <p>TCG</p>
    </div>

    <div class="nav-buttons">
      <p
        class="Botão"
        onclick="window.location.href='Pages/LoginFrontEnd/Login.html'"
      >
        Login
      </p>
      <p class="Botão">Registrar-se</p>
    </div>
  </div>

  <div class="Img">
    <h1>Sua história começa aqui</h1>
  </div>

  <div class="Corpo2">
    <div class="Quadrado1">
      <h1>De novato a Lenda!</h1>

      <p>
        Encare desafios, <strong>ganhe prêmios</strong> e conquiste seu lugar no
        topo do <strong>Ranking</strong> Global de Cobblemon.
      </p>

      <p class="ComeceJa">Comece já</p>
      <img src="/images/placeholder.gif" />
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

@font-face {
  font-family: "minecraftia";
  src: url("/fonts/Minecraftia-Regular.ttf") format("truetype");
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
  padding: 50px;
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
  width: 200px;
  height: 350px;
  width: 300px;
}

.Navbar {
  display: flex;
  flex-direction: row;
  align-items: center;
  background: linear-gradient(135deg, #000000 45%, #521a14 55%);
  height: auto;
  padding: 15px clamp(30px, 5vw, 60px);
  margin: 0;
  gap: 20px;
}

.Navbar h1 {
  margin: 0;
  font-size: clamp(22px, 3vw, 28px);
  flex-shrink: 0;
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
}

.nav-buttons {
  display: flex;
  gap: 15px;
  margin: 0;
  align-items: center;
  flex-shrink: 0;
}

.Botão {
  border: none;
  border-radius: 8px;
  box-shadow: 5px 5px black;
  background-color: #a3a3a3;
  padding: 8px 18px;
  margin: 0;
  cursor: pointer;
  font-size: 13px;
  white-space: nowrap;
}

.Botão p {
  filter: opacity(100%);
}

p,
h1 {
  font-family: "minecraftia";
  color: white;
}

.Img {
  background-image: url("/images/placeholder.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  margin: 0;
  height: 700px;
  width: 100%;
  padding: 20px;
  box-sizing: border-box;
  display: flex;
  justify-content: center;
  align-items: center;
}

.Img h1 {
  color: red;
  margin: 0;
  text-align: center;
  font-size: clamp(20px, 4vw, 32px);
}
</style>
