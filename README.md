# JAVASCRIPT #

### index.html ###

<!DOCTYPE html>
<html lang="pt-br">
	<head>
		<meta charset="UTF-8">
		<title>Aparecida Nutrição</title>
		<link rel="icon" href="favicon.ico" type="image/x-icon">
		<link rel="stylesheet" type="text/css" href="css/reset.css">
		<link rel="stylesheet" type="text/css" href="css/index.css">

	</head>
	<body>

		<header>
			<div class="container">
				<h1>Aparecida Nutrição</h1>
			</div>
		</header>
		<main>
			<section class="container">
				<h2>Meus pacientes</h2>
				<table>
					<thead>
						<tr>
							<th>Nome</th>
							<th>Peso(kg)</th>
							<th>Altura(m)</th>
							<th>Gordura Corporal(%)</th>
							<th>IMC</th>
						</tr>
					</thead>
					<tbody id="tabela-pacientes">
						<tr class="paciente" id="primeiro-paciente">
							<td class="info-nome">Paulo</td>
							<td class="info-peso">100</td>
							<td class="info-altura">2.00</td>
							<td class="info-gordura">10</td>
							<td class="info-imc">0</td>
						</tr>

						<tr class="paciente" >
							<td class="info-nome">João</td>
							<td class="info-peso">80</td>
							<td class="info-altura">1.72</td>
							<td class="info-gordura">40</td>
							<td class="info-imc">0</td>
						</tr>

						<tr class="paciente" >
							<td class="info-nome">Erica</td>
							<td class="info-peso">54</td>
							<td class="info-altura">1.64</td>
							<td class="info-gordura">14</td>
							<td class="info-imc">0</td>
						</tr>

						<tr class="paciente">
							<td class="info-nome">Douglas</td>
							<td class="info-peso">85</td>
							<td class="info-altura">1.73</td>
							<td class="info-gordura">24</td>
							<td class="info-imc">0</td>
						</tr>
						<tr class="paciente" >
							<td class="info-nome">Tatiana</td>
							<td class="info-peso">46</td>
							<td class="info-altura">1.55</td>
							<td class="info-gordura">19</td>
							<td class="info-imc">0</td>
						</tr>
					</tbody>
				</table>

			</section>
		</main>

			<section class="container">
			    <h2 id="titulo-form">Adicionar novo paciente</h2>
			    <form id="form-adiciona">
			        <div class="grupo">
			            <label for="nome">Nome:</label>
			            <input id="nome" name="nome" type="text" placeholder="digite o nome do seu paciente" class="campo">
			        </div>
			        <div class="grupo">
			            <label for="peso">Peso:</label>
			            <input id="peso" name="peso" type="text" placeholder="digite o peso do seu paciente" class="campo campo-medio">
			        </div>
			        <div class="grupo">
			            <label for="altura">Altura:</label>
			            <input id="altura" name="altura" type="text" placeholder="digite a altura do seu paciente" class="campo campo-medio">
			        </div>
			        <div class="grupo">
			            <label for="gordura">% de Gordura:</label>
			            <input id="gordura" type="text" placeholder="digite a porcentagem de gordura do seu paciente" class="campo campo-medio">
			        </div>

			        <button id="adicionar-paciente" class="botao bto-principal">Adicionar</button>
			    </form>
			</section>
 		
 		<script src="js/principal.js"></script>

	</body>
</html>

# principal.js #

var titulo = documnet.querySelector(".titulo");
titulo.textContent = "Aperecida Nutricionista"

var pacientes = document.quarySelectorAll(".paciente")

for(var i = 0; i < paciente.length; i++){

        var paciente= pacientes[i];

        var tdPeso = paciente.quarySelector(".info-peso")
    var peso = tdPeso.textContent;

    var tdAltura = paciente.quarySelector(".info-altura")
    var altura = tdAltura.textContent;

    var pesoEhValido = true; // assumindo de boa fé que o peso é válido
    var alturaEhValida = true; // assumindo de boa fé que a altura é válida

    if (peso <= 0 || peso > 1000) {
        console.log("Peso inválido!");
        pesoEhValido = false;
        tdPeso.textContent = "Peso inválido!";
        paciente.classListadd.add("paciente-invalido")
    }

    if (altura <= 0 || altura >= 3.00) {
        console.log("Altura inválida!");
        alturaEhValida = false;
        tdAltura.textContent = "Altura inválida!";
        paciente.classListadd.add("paciente-invalido")
    }

    if (alturaEhValida && pesoEhValido) {
        var imc = peso / (altura * altura);
        tdImc.textContent = imc.toFixed(2);    
    }
}

var botaoAdicionar = document.quarySelector("#adicionar-paciente");
botaoAdicionar.addEventListeener("click",funcion(event){
   event.preventDefault();

    var for = documnet.querySelector("#form-adiciona");

    var nome = form.nome.value;
    var peso = form.peso.value;
    var altura = form.altura.value;
    var gordura = form.gordura.value;

    var pacienteTr = createElement("tr");

    var nomeTd = documnet.createElement("td");
    var pesoTd = documnet.createElement("td");
    var alturaTd = documnet.createElement("td");
    var gorduraTd = documnet.createElement("td");
    var imcTd = documnet.createElement("td");

    nomeTd.textContent = nome;
    pesoTd.textContent = peso;
    alturaTd.textContent = altura;
    gorduraTd.textContent = gordura;
    imcTd.textContent = imc;

    pacienteTr.appenChild(nomeTd);
    pacienteTr.appenChild(pesoTd);
    pacienteTr.appenChild(alturaTd);
    pacienteTr.appenChild(gorduraTd);
    pacienteTr.appenChild(imcTd);

    var tabela = documnet.querySelector("#tabela-pacientes")

    tabela.appenChild(pacientetr);

});

### index.css ###
 
 *{
	box-sizing: border-box;
 }

body{
	font-family: "Helvetica Neue", "Helvetica", Helvetica, Arial, sans-serif;
	font-size: 14px;
}

header{
	background-color: #333;
	height: 3em;
	color: #FFF;
	margin-bottom: 1em;
}

header h1{
	font-size: 2em;
	display:inline-block;
	vertical-align:	middle;
}
header h2{
	font-size: 2em;
	display:inline-block;
	vertical-align:	middle;
}

header .container:before{
	content: '';
	display:inline-block;
	height: 100%;
	vertical-align:	middle;
}

.container{
	width: 60%;
	height: 100%;
	margin: 0 auto;
}

section{
	margin: 2em 0;
	overflow: hidden;
}

section h2{
	font-size: 3em;
	display: block;
	padding-bottom: .5em;
	border-bottom: 1px solid #ccc;
	margin-bottom: .5em;
}

table{
	width: 100%;
	margin-bottom : .5em;
    table-layout: fixed;

}

td, th {
	padding: .7em;
	margin: 0;
	border: 1px solid #ccc;
	text-align: center;
}

th{
	font-weight: bold;
	background-color: #EEE;
}

label{
	color: #555;
	display: block;
	margin-bottom: .2em;
}

.campo{
	margin: 0;
	padding-bottom: 1em;
	width: 100%;
	border: 1px solid #ccc;
	padding: .7em;
	width: 100%;
}

.campo-medio{
	display: inline-block;
	padding-right: .5em;
}

.grupo{
	width: 32%;
	display: inline-block;
	padding: 10px 0px;
}

button{
	padding: .5em 2em;
	border: 0;
	border-bottom: 3px solid;
	font-size: 1.2em;
	cursor: pointer;
	margin: 0;
	margin-top: -3px;
	color: #fff;
	background-color:#0c8cd3;
	border-color: #04324c;
	width: 20%;
    display: block;
    clear: both;
    margin: 10px 0px;

}

button:active{
	margin-top:0px;
	border: 0;
}

button[disabled=disabled], button:disabled {
    background-color: gray;
	border-color: darkgray;

}

.adicionar-paciente{
    margin-top: 30px;
}

.campo-invalido{
	border: 1px solid red;
}

.paciente-invalido{
	background-color: lightcoral;
}
