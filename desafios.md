# Desafios
Algumas questões mais práticas, que podem ser (ou não) aplicadas em uma lousa/computador.

## CSS
- Como você organizaria os seletores `CSS` de uma lista organizada da com a seguinte estrutura:
```html
<article>
    <section>
        <dl>
            <dt>Front-end</dt>
            <dd>Responsável pelo desenvolvimento que está atrelado à camada "de frente" de uma aplicação, como navegadores</dd>
            <dt>Back-end</dt>
            <dd>Responsável pelo desenvolvimento da camada de servidor, que, geralmente, não é interage diretamente com o usuário final via navegador</dd>
            <dt>OPS/Infra/SRE</dt>
            <dd>Responsável pela camada de infraestrutura (geralmente cloud) que suportará as aplicações</dd>
        </dl>
    </section>
</article>
```

- Como você centralizaria (horizontalmente e verticalmente) o conteúdo (filho) de um bloco (pai), considerando que esse bloco (pai) possui largura e altura já definida?
    - R: A forma mais prática é utilizar flexbox, com as seguintes regras: `display: flex; align-items: center; justify-content: center;`.

## JS
- Imagine o seguinte `array` com 1000 itens sequenciais como: `[{id: 1, nome: 'foo'}, {id: 2, nome: 'bar'}, ... {id: 1000, name: 'jon'}]`. Qual método você utilizaria para encontrar um determinado item pelo seu `id`?
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