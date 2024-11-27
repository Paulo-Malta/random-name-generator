<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Generator Names</title>
   
    <link rel="icon" href="images.png" type="image/x-icon">
</head>
<body>

<div class="container">
    <h1>Gerador de Nomes Aleatórios</h1>
    <p>Clique no botão para gerar um nome aleatório.</p>
    
   
    <div class="nome-gerado" id="nome"></div>

   
    <button class="botao-gerar" onclick="mostrarNome()">Gerar Nome</button>
</div>

<script>

function gerarLetra(éVogal) {
  const vogais = ['a', 'e', 'i', 'o', 'u'];
  const consoantes = ['b', 'c', 'd', 'f', 'g', 'h', 'j', 'k', 'l', 'm', 'n', 'p', 'q', 'r', 's', 't', 'v', 'w', 'x', 'y', 'z'];

 
  if (éVogal) {
    return vogais[Math.floor(Math.random() * vogais.length)];
  } else {
    
    return consoantes[Math.floor(Math.random() * consoantes.length)];
  }
}


function gerarNome(tamanho = 5) {
  let nome = '';
  let próximaÉVogal = Math.random() < 0.5; 

  
  for (let i = 0; i < tamanho; i++) {
    nome += gerarLetra(próximaÉVogal);
    próximaÉVogal = !próximaÉVogal; 
  }

  
  return nome.charAt(0).toUpperCase() + nome.slice(1);
}


function mostrarNome() {
  const nome = gerarNome(5); 
  const nomeElemento = document.getElementById('nome'); 
  nomeElemento.textContent = nome; 
}


mostrarNome();
</script>

<footer>
  <p>Feito por <strong>Paulo Miguel</strong> | <span id="data-criacao"></span></p>
</footer>

<script>
  
  const dataCriacao = new Date().getFullYear();
  document.getElementById('data-criacao').textContent = dataCriacao;
</script>

</body>
</html>

body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #e7e6e6;
}
.container {
    text-align: center;
}
.nome-gerado {
    font-size: 2em;
    margin-top: 20px;
    color: #333;
}
.botao-gerar {
    padding: 10px 20px;
    font-size: 1.2em;
    cursor: pointer;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
    margin-top: 20px;
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 20px 0;
    position: fixed;
    bottom: 0;
    width: 100%;
  }
  
  footer p {
    margin: 0;
  }
  
  footer strong {
    color: #f0a500;
  }
  
  footer span {
    font-weight: bold;
  }
