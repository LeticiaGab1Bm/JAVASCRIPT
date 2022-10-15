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
 		
 		<script src="js/calcula-imc.js"></script>
 		<script src="js/form.js"></script>

	</body>
</html>

# calcula-imc.js #

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
        var imc = calculaImc(peso,altura);
        tdImc.textContent = imc;    
    }
}

function calculaImc(peso,altura){
    var imc = 0;

    imc = peso / (altura * altura);

    return imc.toFixed(2);
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

//adicionando o pacinete na tabela
    var tabela = documnet.querySelector("#tabela-pacientes")
    tabela.appenChild(pacientetr);
    form.reset();

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
