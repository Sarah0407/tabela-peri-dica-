# tabela-peri-dica-
import zipfile
import os

# Caminho da pasta onde os arquivos serão salvos
dir_path = '/mnt/data/tabela_periodica'

# Criar a estrutura de pastas
os.makedirs(dir_path, exist_ok=True)

# Arquivos para criar
files = {
    'index.html': """<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tabela Periódica</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <h1>Tabela Periódica</h1>
    <table class="tabela-periodica">
      <tr>
        <td class="elemento" id="h" data-name="Hidrogênio" data-symbol="H" data-atomic="1">
          <p>H</p>
          <span>1</span>
        </td>
        <td class="elemento" id="he" data-name="Hélio" data-symbol="He" data-atomic="2">
          <p>He</p>
          <span>2</span>
        </td>
        <td class="elemento" id="li" data-name="Lítio" data-symbol="Li" data-atomic="3">
          <p>Li</p>
          <span>3</span>
        </td>
        <td class="elemento" id="be" data-name="Berílio" data-symbol="Be" data-atomic="4">
          <p>Be</p>
          <span>4</span>
        </td>
      </tr>
      <tr>
        <td class="elemento" id="b" data-name="Boro" data-symbol="B" data-atomic="5">
          <p>B</p>
          <span>5</span>
        </td>
        <td class="elemento" id="c" data-name="Carbono" data-symbol="C" data-atomic="6">
          <p>C</p>
          <span>6</span>
        </td>
        <td class="elemento" id="n" data-name="Nitrogênio" data-symbol="N" data-atomic="7">
          <p>N</p>
          <span>7</span>
        </td>
        <td class="elemento" id="o" data-name="Oxigênio" data-symbol="O" data-atomic="8">
          <p>O</p>
          <span>8</span>
        </td>
      </tr>
    </table>
  </div>
  <script src="script.js"></script>
</body>
</html>
""",
    'style.css': """* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
  text-align: center;
}

.container {
  width: 80%;
  margin: 0 auto;
}

h1 {
  margin-top: 20px;
  font-size: 2rem;
}

.tabela-periodica {
  width: 100%;
  margin-top: 20px;
  border-collapse: collapse;
}

.elemento {
  width: 60px;
  height: 60px;
  border: 1px solid #ccc;
  background-color: #fff;
  cursor: pointer;
  transition: background-color 0.3s;
}

.elemento:hover {
  background-color: #e0e0e0;
}

.elemento p {
  font-size: 1.2rem;
  font-weight: bold;
}

.elemento span {
  font-size: 0.8rem;
  display: block;
  margin-top: 5px;
}

td {
  text-align: center;
  vertical-align: middle;
}
""",
    'script.js': """document.querySelectorAll('.elemento').forEach(element => {
  element.addEventListener('click', () => {
    const nome = element.getAttribute('data-name');
    const simbolo = element.getAttribute('data-symbol');
    const atomic = element.getAttribute('data-atomic');
    alert(`Elemento: ${nome}\nSímbolo: ${simbolo}\nNúmero Atômico: ${atomic}`);
  });
})
