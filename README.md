

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
  #story-container {
    margin: 30px auto 0 auto;
    width: 240px;
    height: 430px;
    background: #fff;
    border-radius: 20px;
    box-shadow: 0 0 15px #d98bbd;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
    /* proporção vertical estilo story */
  }
  #story-img {
    width: 220px;
    height: 390px;
    object-fit: cover;
    border-radius: 15px;
    box-shadow: 0 0 8px #d98bbd;
    transition: opacity 0.7s;
    position: absolute;
    left: 10px;
    top: 20px;
    background: #eee;
  }
  /* Barra de progresso opcional no topo do story */
  #progress-bar {
    position: absolute;
    top: 8px;
    left: 15px;
    width: 210px;
    height: 5px;
    background: #e2c4d9;
    border-radius: 3px;
    overflow: hidden;
  }
  #progress {
    height: 100%;
    background: linear-gradient(90deg, #a83279, #f7797d);
    width: 0;
    transition: width 0.1s;
  }
</style>
</head>
<body>

<h1>Meu amor,</h1>
<p>Eu te amo tanto, quero viver pra sempre com você. Você é o meu porto seguro, minha paz, minha vida, meu garoto preferido do mundo inteirinho. Quero poder construir uma vida ao seu lado, quero casar com você e construir uma família linda junto contigo. Eu te amo muito, meu amor! ❤️</p>

<div id="contador">Estamos juntos há: 0 dias, 0h 0m 0s</div>

<p><a href="https://open.spotify.com/track/2o2xhyri4aJUtgMGkf5P0J?si=O4Z0X51mTfWOVLoNjDIXSw" target="_blank" rel="noopener noreferrer">Ouça nossa música especial aqui</a></p>

<div id="story-container">
  <div id="progress-bar"><div id="progress"></div></div>
  <img id="story-img" src="IMG_1498_VSCO.jpeg" alt="Foto do story" />
</div>

<script>
  // Contador de tempo juntos
  const inicio = new Date('2024-05-10T00:00:00');
  function atualizarContador() {
    const agora = new Date();
    let diff = Math.floor((agora - inicio) / 1000);

    const dias = Math.floor(diff / (3600 * 24));
    diff -= dias * 3600 * 24;

    const horas = Math.floor(diff / 3600);
    diff -= horas * 3600;

    const minutos = Math.floor(diff / 60);
    const segundos = diff - minutos * 60;

    document.getElementById('contador').textContent = 
      `Estamos juntos há: ${dias} dias, ${horas}h ${minutos}m ${segundos}s`;
  }
  setInterval(atualizarContador, 1000);
  atualizarContador();

  // Story automático
  const imagens = [
    'IMG_1498_VSCO.jpeg',
    'IMG_1995.jpeg',
    'IMG_9321.jpeg'
  ];
  let storyIndex = 0;
  const storyImg = document.getElementById('story-img');
  const progress = document.getElementById('progress');
  const tempoStory = 3000; // 3 segundos por imagem

  function mostrarStory(i) {
    storyImg.style.opacity = 0;
    setTimeout(() => {
      storyImg.src = imagens[i];
      storyImg.style.opacity = 1;
      progress.style.width = '0';
    }, 700); // Mesmo tempo da transição CSS
  }

  function proximoStory() {
    storyIndex = (storyIndex + 1) % imagens.length;
    mostrarStory(storyIndex);
  }

  // Barra de progresso
  let intervalo, progresso;
  function startStoryTimer() {
    let start = Date.now();
    progresso = setInterval(() => {
      let elapsed = Date.now() - start;
      let percent = Math.min((elapsed / tempoStory) * 100, 100);
      progress.style.width = percent + '%';
      if (percent >= 100) {
        clearInterval(progresso);
      }
    }, 30);
    intervalo = setTimeout(() => {
      proximoStory();
      startStoryTimer();
    }, tempoStory);
  }

  mostrarStory(storyIndex);
  startStoryTimer();

  // Reinicia o timer ao trocar a imagem manualmente (se desejar implementar toque/click futuramente)
</script>

</body>
</html>
