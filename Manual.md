# Manual Angular 09
Criado com base no curso da **Cod3r** [Angular9 - Essencial](https://www.cod3r.com.br/courses/take/angular-9-essencial)

### Visão geral do Angular:

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

### Conceitos Essenciais:

* Inicialização da aplicação. 
    - Quando o projeto for criado teremos um arquivo chamado **main.ts** (*Arquivo TypeScript*)
    - Na sequência esse arquivo ira chamar o módulo da aplicação **AppModule**. Além dos componentes teremos os módulos e os componentes dentro dos módulos. Dentro do **AppModule** terá um atibuto chamado **Bootstrap** que vai apontar para o componente **AppComponent**
    - Em **AppComponent** toda a arvore de componentes será chamada
Esse é o processo de Inicalização.

* O que é um **Componente**?
    - Componente Angular: um pedaço, trecho de codigo que representa um componente visual na sua tela. Este componente visual terá um *HTML, CSS e um arquivo TS*.
    - Cada componente terá seus proprios arquivos *HTML, CSS e um arquivo TS*.
    - Quando um componente é criado é gerado uma *tag* personalizada como *ex. component home*:
    ```
    <app-home></app-home>
    ```
    *Essa é a forma que temos para referenciar todo o código HTML, estilo e lógica criada para este componente.*

    - Exemplo de um arquivo **TypeScript** do componente:
    ```
    import { Component, OnInit } from '@angular/core';

    @Component({
        selector: 'fenix-home',
        templeteUrl: './home.component.html',
        styleUrls: ['./home.component.css]
    })

    export class HomeComponent implements OnInit {
        constructor() { }

        ngOnInit(): void {

        }
    }    
    ```
    - A partir do arquivo **TypeScript** é que o angular vai encontrar o *HTML* e *CSS*.
