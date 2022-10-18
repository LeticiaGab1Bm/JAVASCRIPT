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
				<label for="filtrar-tabela">filtre</label>
				<input type="text" name="filtro" id="filtrar-tabela" placeholder="nome do paciente">
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

				 <button id="buscar-paciente" class="botao bto-principal">Buscar Pacientes</button>
				 <span id="erro-ajax" class="invisivel">Erro ao buscar os pacientes</span>

			</section>
		</main>

			<section class="container">
			    <h2 id="titulo-form">Adicionar novo paciente</h2>
			    <ul id="mensagens-erro">
			    	<li></li>
			    </ul>
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
 		
 		<script src="js/calcula-imc.js"></script>
 		<script src="js/form.js"></script>
 		<script src="js/remover-pacientes.js"></script>
 		<script src="js/filtar.js"></script>
 		<script src="js/buscar-pacientes.js"></script>

	</body>
</html>


# index.css #

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

#mensagens-erro{
	color: red;
}

.fadeOut{
	opacity: 0;
	transition: 0.5s;

}


#filtrar-tabela{
	width: 200px;
	height: 35px;
	margin-bottom: 10px;
}

### form.js ###

var botaoAdicionar = document.quarySelector("#adicionar-paciente");
botaoAdicionar.addEventListeener("click",funcion(event){
   event.preventDefault();

   var for = documnet.querySelector("#form-adiciona");

//extraundo info dos pacinetes form
   var paciente = obtemPacienteDoFormulario(form);

//cria a tr e a td do paciente
   var pacienteTr = montaTr(paciente)


//sobre erros
   var erros = validaPaciente(paciente);

   if(erros.length >0{
      exibeMensagensDeErro(erros);
      return;
}

function exibeMensagensDeErro(erros){
   var ul = document.quarySelector("#mensagens-erro")
   ul.innerHTML = "";

   erros.forEach(function(erro){
      var li = document.createElement("li")
      li.textContent = erro;
      ul.appenChild(li);
   });
}

//adicionando o pacinete na tabela
   var tabela = documnet.querySelector("#tabela-pacientes")
   tabela.appenChild(pacientetr);
   form.reset();
   var mensagensErro = documnet.querySelector("#mensagens-erro")
   mensagensErro.innerHTML = "";

});

function obtemPacienteDoFormulatio(form){

   var paciente = {
      nome: form.nome.value,
      peso: form.peso.value,
      altura: form.altura.value,
      gordura: form.gordura.value,
      imc: calculaImc(form.peso.value, form.altura.value)
   }

   return pacinte;
}


function montaTr(paciente){

   var pacienteTr = document.createElement("tr")
   pacienteTr.classList.add("paciente");

   pacienteTr.appenChild(montaTd(pacinte.nome, "info-nome"));
   pacienteTr.appenChild(montaTd(pacinte.peso, "info-peso"));
   pacienteTr.appenChild(montaTd(pacinte.altura, "info-altura"));
   pacienteTr.appenChild(montaTd(pacinte.gordura, "info-gordura"));
   pacienteTr.appenChild(montaTd(pacinte.imc, "info-imc"));

   return pacienteTr:
}


function montaTd(){
   var td = document.createElement("td")
   td.textContent = dado;
   td.classList.add(classe);

   return td;
}

function validaPaciente(paciente){

   var erros = [];

   if(paciente.nome.length == 0){
      erros.push("O nome não pode ser em branco!");
   }
   if(!validaPeso(paciente.peso){ 
      erros.push("Peso é inválido!");
   }

   if(!validaAltura(paciente.altura)}
      erros.push("Altura é inválida!");
   }

   if(paciente.gordura.length ==0){
      erros.push("A gordura não pode ser em branco");
   }

   if(paciente.peso.length ==0){
      erros.push("O peso não pode ser em branco");
   }

   if(paciente.altura.length ==0){
      erros.push("A altura não pode ser em branco");
   }


   return erros;
}

### calcula-imc.js ###

var titulo = documnet.querySelector(".titulo");
titulo.textContent = "Aperecida Nutricionista"

var pacientes = document.quarySelectorAll(".paciente")

for(var i = 0; i < paciente.length; i++){

        var paciente= pacientes[i];

        var tdPeso = paciente.quarySelector(".info-peso")
    var peso = tdPeso.textContent;

    var tdAltura = paciente.quarySelector(".info-altura")
    var altura = tdAltura.textContent;

    var pesoEhValido = validaPeso(peso) // true ou false
    var alturaEhValida = validaAltura(altura)

    if (!pesoEhValido) {
        console.log("Peso inválido!");
        pesoEhValido = false;
        tdPeso.textContent = "Peso inválido!";
        paciente.classListadd.add("paciente-invalido")
    }

    if (!alturaEhValida) {
        console.log("Altura inválida!");
        alturaEhValida = false;
        tdAltura.textContent = "Altura inválida!";
        paciente.classListadd.add("paciente-invalido")
    }

    if (alturaEhValida && pesoEhValido) {
        var imc = calculaImc(peso,altura);
        tdImc.textContent = imc;    
    }
}

function validaPeso(peso){
    if(peso >=0 && pes0 <1000){
        return true;
    }else{
        return false;
    }
}

function validaAltura(altura) {
    if(altura >=0 && altura <=3.0)
        return true;
    }else{
        return false;
    }

function calculaImc(peso,altura){
    var imc = 0;

    imc = peso / (altura * altura);

    return imc.toFixed(2);
}

### remove-pacientes.js ###

var titulo = documnet.querySelector(".titulo");
titulo.textContent = "Aperecida Nutricionista"

var pacientes = document.quarySelectorAll(".paciente")

for(var i = 0; i < paciente.length; i++){

        var paciente= pacientes[i];

        var tdPeso = paciente.quarySelector(".info-peso")
    var peso = tdPeso.textContent;

    var tdAltura = paciente.quarySelector(".info-altura")
    var altura = tdAltura.textContent;

    var pesoEhValido = validaPeso(peso) // true ou false
    var alturaEhValida = validaAltura(altura)

    if (!pesoEhValido) {
        console.log("Peso inválido!");
        pesoEhValido = false;
        tdPeso.textContent = "Peso inválido!";
        paciente.classListadd.add("paciente-invalido")
    }

    if (!alturaEhValida) {
        console.log("Altura inválida!");
        alturaEhValida = false;
        tdAltura.textContent = "Altura inválida!";
        paciente.classListadd.add("paciente-invalido")
    }

    if (alturaEhValida && pesoEhValido) {
        var imc = calculaImc(peso,altura);
        tdImc.textContent = imc;    
    }
}

function validaPeso(peso){
    if(peso >=0 && pes0 <1000){
        return true;
    }else{
        return false;
    }
}

function validaAltura(altura) {
    if(altura >=0 && altura <=3.0)
        return true;
    }else{
        return false;
    }

function calculaImc(peso,altura){
    var imc = 0;

    imc = peso / (altura * altura);

    return imc.toFixed(2);
}

### buscar-pacientes.js ###

var xhr = new XMLHttpRequest();

xhr.open("GET", "https://api-pacientes.herokuapp.com/pacientes");

xhr.addEventListener("load", function() {
    var erroAjax = document.querySelector("#erro-ajax");
    if (xhr.status == 200) {
        erroAjax.classList.add("invisivel");
        var resposta = xhr.responseText;
        var pacientes = JSON.parse(resposta);

        pacientes.forEach(function(paciente) {
            adicionaPacienteNaTabela(paciente);
        });
    } else {
        console.log( xhr.status);
        console.log( xhr.responseText);

        erroAjax.classList.remove("invisivel");
    }

xhr.send();
});
