# Perguntas
Algumas perguntas para serem feitas ao longo da entrevista.

## Stack

### HTML
- Você saberia explicar um pouco sobre semântica, como aplicar corretamente nas suas tags e quais seus benefícios?
    - R: Semântica está relacionado à dar significado às tags ap navegador. Antigamente todas as tags eram escritas com div. Hoje com o HTML5 existem tags que envolvem os elementos com significado real, como: `header`, `footer`, `article`, `section` e outras. Deve-se levar em consideração a semântica correta da informação que você deseja "taguear" ao escrecer um elemento.

### CSS
- Você já utilizou ou já leu algo sobre metodologias CSS? (BEM)
    - R: Resposta aberta
- Você saberia diferenciar um pré-processador de um pós-processador?
    - R: Pré-processadores são utilizados para processar uma linguagem que resultara em arquivo(s) CSS em um processo de build (como Sass/Less) e pós-processadores (como o PostCSS) atuam em momento pós build, agregando alguma regra no CSS gerado (como adicionar fallback nas regras não suportadas em alguns navegadores). Basicamente segue um fluxo como: linguagem (Sass/Less) --> {pré-processador} --> CSS --{pós-processador}--> arquivos de CSS finais + novas regras
- Como você organizaria os seletores CSS de uma lista organizada da seguinte maneira:
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

### JS
- Qual a diferença de variáveis declaradas com var variáveis declaradas com let/const?
    - R: Antigamente todas as variáveis eram declaradas com `var`. Existiam alguns problemas de escopo (como hoisting) e de leitura ao utilizar essa forma (por exemplo, ao dar um `console.log` de uma variável que ainda não tinha sido definida, você receberia `undefined` ao invés de um erro). Variáveis declaradas com `let/const` previnem que isso aconteça (gerando um erro no caso mencionado) e também possuem algumas diferenças, como: variáveis declaradas com `const` não permitem reatribuição de valor e variáveis. Além disso, variáveis declaradas com `let/const` possuem escopo de bloco (ou léxico), ou seja, sua declaração está restrita ao bloco que é declarada. O que não acontece com `var` (por exemplo, ao tentar rodar um `for` declarando uma variável de controle `i`, você consegue acessar o valor dela após as repetições), pois tem escopo de função.
- Você sabe a diferença entre uma function comum e uma arrow function?
    - R: Funções declaradas com `function` possuem `this` "dinâmico", pois dependem de um contexto de execução. Já `arrow functions`, possuem o `this` estático, acessando o valor mediante do local onde são declaradas. Além disso, `arrow functions` também são conhecidas por deixarem a escrita mais enxuta e por ter a possibilidade de deixar o argumento `return` implícito.
- Mais alguma funcionalidade ES6+ que você tenha gostado?
- Você sabe o que é uma aplicação isomórfica/universal?
    - R: São aplicações que podem ser executadas tanto no backend, quando no frontend, como aplicações realizadas utilizando server-side rendering.
- Você sabe o que é um Callback Hell?
    - R: É um código ("ambiente") resultante de utilizações de `callbacks` passadas e executadas de forma desorganizada.
- Como evitar um callback hell?
    - R: Modularizando funções de forma mais organizadas e também usando `promises`.
- Você saberia explicar o que são Promises?
    - R: São objetos JS que possibilitam executar código assíncrono de forma mais organizada. Literalmente são "promessas" de que um valor será retornado, com ou sem sucesso.
- Como evitar um Promise Hell?
    - R: Modularizando suas funções de forma organizada, executando `promises` em paralelo e também usando `async/await`. 
- Como executar Promises em paralelo?
    - R: Com `Promise.all()`, que recebe um array de `promises` e retorna outra `promise` que, ao ser finalizada com sucesso, retorna um array com os resultados.
- Você sabe como funciona o `async/await`?
    - R: `async/await` é uma forma `syntax sugar` de utilizar `Promises`, quem utiliza também o conceito de `function generators` por debaixo dos panos.
- Você saberia explicar sobre .map, .filter e .reduce?
    - R: São algumas formas de manipular arrays. Todas as funções recebem uma função de callback. `.map` recebe uma função de e aplica uma determinada operação à todos os itens do array retornando um novo array. `.filter` recebe uma função responsável por checar condicionalmente quais itens devem estar no novo array. `.reduce` recebe uma função responsável por acumular e retornar um novo valor qualquer.
- Qual a difereça entre .filter e um .find?
    - R: `.filter` recebe um `callback` que é executado em todos os elementos do `array` com intenção de filtrá-los mediante à uma condição. Já o `.find` retorna a primeira ocorrência no array de uma determinada condição, parando a execução do loop nos demais itens que ainda não foram percorridos.

### React
- Você sabe qual a diferença entre um componente de classe e um componente funcional? Qual a melhor forma de trabalhar com cada um deles?
    - R: Componentes de classe extendem (geralmente) o `React.Component`, também apresentam estado e métodos de `life-cycle`. Componentes funcionais são declarados como funções e, hoje em dia, também podem apresentar estado utilizando os `Hooks` e determinados `side-effects`.
- Você saberia explicar o que são Hooks e quais benefícios eles trazem?
    - R: `Hooks` é uma nova abordagem para manter estados em componentes (funcionais) e determinar `side-effects`, executando funções de forma próxima ao `life-cycle` dos componentes de classe (só que com certos detalhes em sua abordagem).
- Você saberia explicar o que é um Higher-Order component?
    - R: É um padrão de escrita de componentes, que visa "decorar" um componente com novas `props` ou valores.
- Você sabe o que é SSR (server-side rendering)?
    - R: É a ação de renderizar sua aplicação no lado do servidor.
- Você saberia dizer por quê uma aplicação em React (e outras bibliotecas/frameworks), mesmo com suas abstrações (como o JSX e tudo mais) tem uma boa performance se comparada à uma aplicação em JS pura?
    - R: Porque ele mantém uma cópia virtual do DOM em memória, otimizando qualquer atualização de forma performática.
- Qual a diferença de uma prop pra um state?
    - R: `Props` são valores recebidos como parâmetros ao instanciar um componente `React`. `State` são valores definidos como estado do seu componente. Ambos estão relacionados aos métodos de `life-cycle`
- O que você vê de positivo e negativo entre React e algumas outras tecnologias do mercado (como Angular e Vue)?
    - R: resposta aberta

### Node
- O que é NodeJS?
    - R: Uma plataforma que utiliza a engine V8 do Google (utilizada no Chrome) para executar JavaScript no servidor.
- Você saberia explicar um pouco sobre como funciona a arquitetura do Node, se é single-thread ou multi-thread e como funciona um pouco mais a fundo?
    - R: Resposta aberta, mas vale atentar ao fato que JavaScript é single-thread embora lide muito bem com requisições e I/O devido ao EventLoop.
- Você saberia a diferença na escrita entre um módulo CommonJS e um módulo EcmaScript?
    - R: CommonJS é o padrão de escrita de módulos do Node (`module.exports`, `exports.{nome}` e `require('module')`) e EcmaScript é o padrão de módulos "nativos" do JavaScript (que ainda está em implementação mas é seguido pelos bundlers como o webpack, e tem a sintaxe utilizada na maioria das aplicações como `import nome from 'nome'`, `export const valor = 'valor'`, e `export default nome`). 
- **Express** Você sabe o que é um middleware?
    - R: São funções executadas de forma ordenada nas rotas do express. Geralmente utilizadas para consultar e agregar valores aos dados das requisições.

### Testes
- Você costuma aplicar testes quando está desenvolvendo?
- Saberia explicar a diferença de um teste unitário, pra um teste integrado e um teste end-to-end? Quais ferramentas você conhece para aplicar esses testes?
    - R: Teste unitário leva em consideração uma simples unidade de código (uma função ou um componente). Testes de integração olham para um contexto maior (várias funções ou componentes em conjunto). E Testes end-to-end (ou e2e) visam testar uma aplicação de ponta a ponta, simulando um usuário e, por isso, geralmente utilizam ferramentas que simulam navegadores reais. Algumas ferramentas utilizadas para esses testes são: Jest, Sinon, Mocha, Enzyme, React Testing Library, Cypress, WebdriverIO, Nightwatch.
- O que você leva em consideração na hora de realizar um teste unitário, no frontend e no BFF?
    - R: Resposrta aberta.

### Tooling
- Você sabe o que é o Webpack? Já chegou a mexer com ele e configurar algumas rotinas de build de dev/prod?
    - R: Webpack é um `module bundler` (agrega módulos, realiza build dos arquivos e resolve dependências), assim como o Browserify.
- No package.json, você sabe a diferença entre `dependencies`, `devDependencies` e `peerDependencies`?
    - R: `dependencies` são dependencias que são necessárias ao rodar a aplicação (como `react`, `react-dom`). `devDependencies` são dependencias que são necessárias apenas em ambiente de desenvolvimento e `peerDependencies` é uma categoria que visa especificar pacotes que dependem de outros pacote, mais utilizados em bibliotecas compartilhadas, evitando a necessidade de instalar um pacote em uma versão específica e utilizando a versão provida pelo ambiente.
- Pra que serve o arquivo package-lock e yarn.lock?
    - R: Para manter a "árvore" de dependências "travada" e evitar conflito em diferentes ambientes/máquinas.
- Por quê você usou yarn ao invés do NPM?
    - R: Resposta aberta.

--------------------------------------------------------------------

## Gerais
- Imagine um cenário: você recebe um novo projeto pra desenvolver do zero. Como você definiria a arquitetura desse projeto? Quais tecnologias usaria?
- Como você começou no mundo do desenvolvimento?
- Como você se mantém atualizado (cursos, posts, blogs)? Quais?

