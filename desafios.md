# Desafios
Algumas questões mais práticas, que podem ser (ou não) aplicadas em uma lousa/computador.

- Se você tivesse um array com 1000 itens e quisesse achar um item qualquer. Qual método você utilizaria: `.find` ou `.filter`? Por quê?
R: O ideal é utilizar `.find`, já que está buscando apenas um item. Pois ao utilizar `.find` e encontrar o valor desejado, o loop de execução é terminado imediatamente, ao contrário do `.filter`, que percorerrá todo o array.

- Implemente uma função que retorna se uma palavra é palíndroma(o) (tem o mesmo significado de trás pra frente), por exemplo:
```js
isPalindrome('anna') // => true
isPalindrome('bob') // => true
isPalindrome('jarbas') // => false
```