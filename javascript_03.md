# Javascript 03

- É possível guardar funções como se fossem variáveis em atributos de classes, assim como também pode-se passar essas funções nos parâmetros de construtores
- Se a função é atributo, para passar como parâmetro é só escrever o nome
- O this possui um contexto dinâmico (de onde ele está sendo executado), isso com function
 - Já o this de uma Arrow Function pega o da classe logo acima (e não do contexto mais próximo), ele é léxico e não varia ao decorrer das chamadas

## Funções
- [Funções em Javascript](https://medium.com/reactbrasil/como-o-javascript-funciona-entendendo-as-fun%C3%A7%C3%B5es-e-suas-formas-de-uso-eb387c7fa138)
- Uma vez atribuídas a uma variável, elas podem ser invocadas pelo nome da variável
- Passadas como argumento podem ser invocadas pelo nome do parâmetro da função
- Se invocadas imediatamente, o nome é irrelevante

### Callback Function
- É quando uma função é passada como argumento de outra função, e a mesma será chamada quando algo ocorrer
- Parâmetro: variável declarada na definição da função
- Argumento: valor passado para a função na invocação
- Parâmetros com valores default:
```Javascript
function sum(a = 1, b = 3){
    return a + b;
}
sum() // retorna 4
sum(2) // retorna 5
sum(2,4) // retorna 6
```
- Rest parameters:
```JavaScript
function myFunction(param1, ...moreParams){
    console.log(param1);
    console.log(moreParams);
}
```
 - Se não puder utilizar ES6, um substituto para o Rest Parameters é ```arguments```
- Criar função e invocar imediatamente: ```function(){console.log("IIEF"})();```

## Invocação de função
- Normal:
```JavaScript
function sum(x, Y){
    console.log(arguments);
    console.log(this)

    return X + y;    
}
console.log(sum(1, 4));
```
- Como método:
```JavaScript
let obj = {};
obj.sum = function(x, y){
    console.log(arguments);
    console.log(this)

    return x + y;    
}
console.log(obj.sum(1,4));
//
{"0":1,"1":4}
{ sum: [Function]}
5
```
- Método ```apply``` e ```call``` servem para definir o contexto a ser executado para um função quando utilizar o ```this```
- Function generator: função que retorna mais de uma valor, a cada vez invocada ela faz um retorno

Storybook
Sass
