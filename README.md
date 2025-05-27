# amordaminhavida<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Nosso Amor</title>
<style>
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    max-width: 600px;
    margin: 20px auto;
    padding: 20px;
    background: #fff0f6;
    color: #4a0033;
    text-align: center;
    border-radius: 10px;
    box-shadow: 0 0 15px #d98bbd;
  }
  h1 {
    color: #a83279;
  }
  p {
    font-size: 1.2em;
    line-height: 1.5em;
  }
  #contador {
    font-weight: bold;
    font-size: 1.5em;
    margin: 20px 0;
  }
  a {
    color: #a83279;
    text-decoration: none;
    font-weight: 600;
  }
  a:hover {
    text-decoration: underline;
  }
  #fotos {
    margin-top: 25px;
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap;
  }
  #fotos img {
    width: 120px;
    height: 120px;
    object-fit: cover;
    border-radius: 10px;
    box-shadow: 0 0 8px #d98bbd;
  }
</style>
</head>
<body>

<h1>Meu amor,</h1>
<p>Eu te amo tanto, quero viver pra sempre com você. Você é o meu porto seguro, minha paz, minha vida, meu garoto preferido o mundo inteirinho. Quero poder construir uma vida ao seu lado, quero casar com você e construir uma família linda junto contigo. Eu te amo muito, meu amor! ❤️</p>

<div id="contador">Estamos juntos há: 0 dias, 0h 0m 0s</div>

<p><a href="https://open.spotify.com/track/3UStHHOyFXetR5621bKJBz?si=4pcKATGCS3my1TBltrvYPg" target="_blank" rel="noopener noreferrer">Ouça nossa música especial aqui</a></p>

<div id="fotos">
IMG_1498_VSCO.jpeg
IMG_1995.jpeg
IMG_9321.jpeg

<script>
  const inicio = new Date('2024-05-10T00:00:00'); // Data que começaram

  function atualizarContador() {
    const agora = new Date();
    let diff = Math.floor((agora - inicio) / 1000); // diferença em segundos

    const dias = Math.floor(diff / (3600 * 24));
    diff -= dias * 3600 * 24;

    const horas = Math.floor(diff / 3600);
    diff -= horas * 3600;

    const minutos = Math.floor(diff / 60);
    const segundos = diff - minutos * 60;

    document.getElementById('contador').textContent = `Estamos juntos há: ${dias} dias, ${horas}h ${minutos}m ${segundos}s`;
  }

  setInterval(atualizarContador, 1000);
  atualizarContador();
</script>

</body>
</html>
