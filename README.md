<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HACKER SPIDER</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 20px;
            background-color: #e0f7fa; /* Azul claro */
            color: #4a148c; /* Roxo escuro */
        }
        h1 {
            color: #d81b60; /* Rosa */
        }
        button {
            padding: 10px 15px;
            font-size: 16px;
            cursor: pointer;
            background-color: #d81b60; /* Rosa */
            color: white;
            border: none;
            border-radius: 5px;
        }
        button:hover {
            background-color: #c2185b; /* Rosa mais escuro ao passar o mouse */
        }
        ul {
            margin-top: 20px;
            list-style-type: none; /* Remove os marcadores da lista */
        }
        li {
            background-color: #fff; /* Fundo branco para os itens da lista */
            border-radius: 5px;
            padding: 10px;
            margin-bottom: 10px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1); /* Sombra leve para os itens */
        }
    </style>
</head>
<body>

<h1>Gerador de Sinais</h1>
<button id="gerarSinais">Gerar Sinais</button>

<ul id="listaSinais"></ul>

<script>
    document.getElementById('gerarSinais').addEventListener('click', function() {
        const lista = document.getElementById('listaSinais');
        lista.innerHTML = ''; // Limpa a lista antes de adicionar novos sinais
        
        const sinais = [];
        const agora = new Date(); // Pega a data e hora atuais

        for (let i = 0; i < 8; i++) { // Gera sinais para 8 intervalos
            const novaHora = new Date(agora.getTime() + i * 3 * 60000); // Adiciona 3 minutos a cada iteração
            const horaFormatada = novaHora.toLocaleTimeString('pt-BR', { hour: '2-digit', minute: '2-digit', second: '2-digit' });
            sinais.push(`${horaFormatada}`);
        }

        sinais.forEach(sinal => {
            const li = document.createElement('li');
            li.textContent = sinal;
            lista.appendChild(li);
        });
    });
</script>

</body>
</html>
