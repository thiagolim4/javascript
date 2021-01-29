# Javascript 02

## this e let
- ```this```: variável implícita que sempre aponta para a instância que está executando a operação naquele momento
- Classe em Javscript puro:
```Javascript
class Negociacao{
  constructor(){
    this.data = new Date();
    this.quantidade = 1;
    this.valor = 0.0;
  }
}
```
- Propriedades de classes somente de leitura, usa-se underline: ```this._data = data```. Para eles cria-se get's e pode usar como propriedade no momento de pegar valor:
```Javascript
get quantidade() {
    return this._quantidade;
}
n1.quantidade = 1000 /*Não altera pois é um getter*/
n1._quantidade = 5000 /*Consegue alterar*/
```
- Declaração de variável com ```let```: é uma variável com escopo de bloco
- ```this```: é o contexto pelo qual o método é chamado. Se quer tratar esse método como uma função separada, mas ainda mantendo essa associação de contexto, usa-se o ```bind(document)```
- Função ```map```: executa uma função para cada elemento de um array, aceita certos parâmetros na sua função interna
```Javascript
adiciona(event) {

    event.preventDefault();

    let data = new Date(...
        this._inputData.value
        .split('-')
        .map(function(item, indice) {
            if(indice == 1) {
                return item - 1;
            }
            return item;
        })
    );
    console.log(data);
}
```
- Spread operator: passar vários dados no parâmetro
- Arrow Functions: função flecha, não precisa colocar o nome ```function```
```JavaScript
class Pessoa {
    constructor(nome) {
        this.nome = nome;
    }
}

function exibeNome() {
    alert(this.nome);
}

let pessoa = new Pessoa('Salsifufu');
exibeNome('Lampreia'); // PRIMEIRA CHAMADA <=============
exibeNome = exibeNome.bind(pessoa);
exibeNome(); // SEGUNDA CHAMADA, exibe Salsifufu <=============
```
- Classes podem ter métodos estáticos para não precisar chamar o objeto da classe
- Template string: ```console.log(\backstick\A idade de ${nome} é ${idade}\backstick\)```
- Lançar erros: ```throw new Error('Mensagem de erro')```. Se uma classe só tem métodos estáticos, pode colocar isso dentro do Construtor para ninguém instanciá-la.
- Tem método push para list

## View
- Pegando elementos do HTML com Javascript:
```JavaScript
let $ = document.querySelector.bind(document);
this._inputData = $('#data');
```
- Pode usar o innerHTML para converter uma string (de HTML) pro DOM poder utilizar
- Cria uma div com um id, esse será o elemento que recebe
- Faz um construtor que recebe o elemento (DOM, $), e a propriedade innerHTML desse elemento recebe o retorno do método em string
 - Transformar em string: model.negociacoes.map(arrow function).join('')
 - Função imediata chama a própria função (usada em bloco, dentro de ${})
 - Função reduce() processa um array e depois devolve um resultado

## Texto
- É possível deixar uma mensagem padrão:
```JavaScript
 class Mensagem {
    constructor(texto='') {
        this._texto = texto;
    }
  }
```

## Herança
- Pode usar extends, mas não esquecer na hora da importação que a classe mãe deve vir antes das outras
- Super() é um contrutor que constroi a classe mãe
