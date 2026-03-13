# javascript-
<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<title>Gerador de Tabuada Interativo</title>

<style>
body {
    font-family: Arial; 
    text-align: center;
    margin-top: 150px;
    background-color: rgb(182, 182, 236);
    h1{color:white}
    p {color:white}
}

input, button {
    padding: 8px;
    font-size: 16px;
}

/* Container principal das tabuadas */
#containerTabuadas {
    display: flex;           /* exibe as tabuadas lado a lado */
    justify-content: center;
    flex-wrap: wrap;         /* permite quebrar linha se não couber */
    gap: 30px;               /* espaço entre as tabuadas */
    margin-top: 20px;
}

/* Cada tabuada individual */
.tabua {
    background-color: #f0f0f0;
    padding: 15px;
    border-radius: 5px;
    text-align: left;        /* para organizar verticalmente os cálculos */
    min-width: 120px;
}
</style>
</head>
<body>

<h1>Gerador de Tabuada Interativo</h1>

<p>Digite um número entre 1 e 10:</p>

<input type="number" id="numero" min="1" max="10">
<button onclick="gerarTabuada()">Gerar Tabuada</button>

<!-- Container que vai armazenar todas as tabuadas -->
<div id="containerTabuadas"></div>

<script>
function gerarTabuada() {
    let numero = document.getElementById("numero").value;

    if(numero === "" || numero < 1 || numero > 10){
        window.alert("⚠️ Digite um número válido entre 1 e 10.");
        return;
    }

    // Criar nova div para a tabuada do número atual
    let novaTabuada = document.createElement("div");
    novaTabuada.className = "tabua";

    // Título da tabuada
    let titulo = document.createElement("h3");
    titulo.textContent = `Tabuada do ${numero}`;
    novaTabuada.appendChild(titulo);

    // Gerar a tabuada verticalmente (1 a 10)
    for(let i = 1; i <= 10; i++){
        let linha = document.createElement("div");
        linha.textContent = `${numero} x ${i} = ${numero * i}`;
        novaTabuada.appendChild(linha);
    }

    // Adicionar a nova tabuada ao container principal, mantendo as antigas
    document.getElementById("containerTabuadas").appendChild(novaTabuada);

    // Limpar campo de input
    document.getElementById("numero").value = "";
}
</script>

</body>
</html>

