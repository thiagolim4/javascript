# JavaScript 01

## Tags iniciais
- Escrever código sempre entre ```<scrpit></script>```
- ```alert()```, ```console.log()```
- **DOM**: Document Object Model, representação do HTML para o JavaScript (ponte entre ambos)
 - O document é uma variável muito importante do Javascript. Ela contém o DOM ou Document Object Model, que é como o navegador enxerga o HTML utilizado por ele para renderizar a página.

O navegador, ao ler o seu arquivo HTML, cria uma cópia em memória daquele HTML e a partir dessa cópia ele vai desenhando a sua página, colocando as tags e aplicando os estilos. Esta cópia é o que chamamos de DOM uma representação em memória do HTML do seu arquivo, que o navegador usa para desenhar a página, e a variável document é quem contêm o DOM.

Por isso, quando dizemos que com o Javascript nós estamos manipulando o DOM, estamos manipulando o que o navegador renderizou. Então ao trocar algum texto do DOM, o navegador imediatamente desenha novamente aquele texto, pois o DOM é o que o navegador usa para desenhar o seu site.

Outra caracteristica interessante, é que como manipulamos o DOM , quando trocamos um texto de um <h1> ou um estilo de um elemento, na verdade estamos alterando a representação em memória , o que faz com que o arquivo fonte que contêm seu HTML fique intacto!

- QuerySelector procura o conteúdo de uma tag na página HTML
- Boa prática é colocar os scripts no final do ```<body>```

## Arrays, Loops e Estilos
- ```querySelectorAll``` retorna um array dos elementos internos daquela tag
 - Possui a proriedade ```length``` quando retorna um ```vetor[i]```
```JavaScript
for(var i = 0; i < 5; i++){
  //...
  var imc = 5.289
  imc.toFixed(2); // retorna duas casas decimais
}
```
- ```elemento.style.color = "red"``` modifica o estilo do elemento HTML
- ```elemento.style.backgroundColor = "red"```
- ```elemento.classList.add("classeDoCSS");``` adiciona uma classe de estilo para o elemento

## Eventos
- ```elemento.addEventListener("click", mostraMensagem)```: adiciona um ouvinte pra esse elemento e executa a funçao passada no parâmetro
```JavaScript
function mostraMensagem(){
  console.log("Olá eu fui clicado!");
}
```
- Função anônima: pode chamar uma função direto dentro do parâmetro
```JavaScript
elemento.addEventListener("click", function(){
  //...
});
//previne o comportamento padrão
elemento.addEventListener("click", function(event){
  event.preventDefault();
  console.log("Fui clicado!");
  //...
});
```
- Pra exibir, usa ```document.createElement("td")``` e depois adiciona o conteúdo nele com ```var.textContent = conteudo```
- Função ```elemento.appendChild(elementoFilho)``` adiciona tags dentro de tags
- Event shortcut é o evento adicionado direto na propriedade, como ```botao.onclick = botaoHandler```
- Objetos em JavaScript
```JavaScript
var paciente = {
  atributo1: valor1,
  atributo2: valor2
};
```
- ```form.reset()``` apaga os campos do form depois de apertar o botão
- Função ```push("String")``` coloca dados dentro do array
- ```elemento.innerHTML = ""``` altera o HTML interno

## Expressões regulares
- Busca comum em textos grandes (eel vai atualizando conforme digita-se as letras), parâmetros são o valor buscado e se é *case sensitive*
```Javascript
var expressao = new RegExp(this.value, "i", );
```
- Esconde certos elementos da tela:
```CSS
.invisivel{
    display: none;
}
```

## AJAX
- API é uma interface de programação que disponibiliza funcionalidades pro usuário
```JavaScript
// responsável por fazer requisições
var xhr = new XMLHttpRequest();
// tipo da requisicao
xhr.open("GET", "link da requisição");

xhr.addEventListener("load", function(){
  //executa essa funcao depois que retornar a resposta
  console.log(xhr.responseText);
  var resposta = xhr.responseText;
  var pacientes = JSON.parse(resposta);
});

xhr.send();
```
- AJAX é requisição com JavaScript assíncrona (sem travar o navegador ou exigir dele um reload)
- ```xhr.status``` é a propriedade do status da requisição, indicando o tipo de erro (se houver)
