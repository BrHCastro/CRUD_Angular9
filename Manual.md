# Manual Angular 09
Criado com base no curso da **Cod3r** [Angular9 - Essencial](https://www.cod3r.com.br/courses/take/angular-9-essencial)

# Visão geral do Angular:

* Um framework javaScript desenvolvido pela Google para criação de **aplicaçoes Web SPA** (*Single Page Aplication*) baseado em **componentes**.

* Uso frequente do **CLI** (*Comand line Interface*). Base para criar uma aplicação.
    - Instalação do **CLI** apartir do **NPM**:
    ```
    npm i -g @angular/cli (i de install e -g de global)
    ```
    - Criação da **Aplicação**:
    ```
    ng new minha-app (ng de aNGular)
    ```
* Uso por padrão de **TypeScript**. Linguagem criada pela *Microsoft*, o código escrito em TS é **compilado** para **JavaScript**.
    - Orentada a Objetos & **Tipagem forte** (Tem como definir tipos associado as variáveis).
    - Outros recursos como por exemplo o **Decorator** e **Interfaces**.
    - Superset do **JavaScript**. coloca algumas funcionalidade a mais que o navegador não interpretará e será compilado. E quando gerar o projeto ele estará apenas com *HTML, CSS e principalmente JavaScript*.

* Arvore de **Componentes**.
    - Inicia com um componente principal *ex. myApp*
    - Apartir do compoente principal você vai referenciando outros componentes *ex. Header, Content*.
    - Dentro do Header você vai ter um componente de navegação *ex. Nav*
    - Dentro do Content você terá um componente para título e/ou componente para crud *ex. ContentTitle, ContentProductCrud*.
    - Entre outros...
