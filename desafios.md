# Desafios
Algumas questões mais práticas, que podem ser (ou não) aplicadas em uma lousa/computador.

- Se você tivesse um array com 1000 itens e quisesse achar um item qualquer. Qual método você utilizaria: `.find` ou `.filter`? Por quê?
    - R: O ideal é utilizar `.find`, já que está buscando apenas um item. Pois ao utilizar `.find` e encontrar o valor desejado, o loop de execução é terminado imediatamente, ao contrário do `.filter`, que percorerrá todo o array.

- Implemente uma função que retorna se uma palavra é palíndroma(o) (tem o mesmo significado de trás pra frente), por exemplo:
```js
isPalindrome('anna') // => true
isPalindrome('bob') // => true
isPalindrome('jarbas') // => false
```

- Imagine o seguinte `array`: `[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`. Como você faria para transformá-lo em um `array` como: `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11]`?
    - R: O mais prático é utilizar um `.map` e passar como `callback` a função que somará um em cada item do array, algo como `.map(value => value + 1)`.

- Imagine o seguinte `array`: `[0, 1, 2, 3, 4]`. Como você faria para transformá-lo em um `array` como: `[0, 2, 4]`?
    - R: O mais prático é utilizar um `.filter` e passar como `callback` a função validará se o item é par, algo como `.map(value => value % 2 === 0)`.