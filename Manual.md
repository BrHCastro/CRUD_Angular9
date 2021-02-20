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

* Organização Usando **Módulo**:
    - O angular não organiza a aplicação apenas em componentes, ele tambem organiza por em *Módulos*, isto é, todos os componentes vão estar dentro de algum *módulo*. Seja um único módulo da aplicação ou organizar em diversos módulos.
    - Quando criamos um componente dentro de um módulo temos a escolha de dizer se este componente ficara visivel fora do módulo ou será visivel apenas dentro do módulo.

* Anatomia do **Módulo**:
    - Em um único módulo teremos cinco atributos que são: *Declarations, Imports, Exports, Providers e Bootstrap*.
    - Declarations: Vai declarar todos os *componentes, diretivas e pipes*.
    - Para tornar um *componente, diretiva e pipe* visivel para fora do módulo temos que colocar este componente tambem dentro da parte onde temos o *Exports*
    - Imports importará outros módulos. Pode ser um módulo da própria aplicação ou um módulo externo como uma bibliotéca de componentes, por exemplo.
    - Providers é onde sera declarado os *services*
    - Bootstrap é onde definimos o nosso componente que sera carregado no módulo inicial.

* Organização Usando **Módulo**:
    - AppModule: Bootstrap, Declarations, Imports.
    - Modulos X,Y e Z: Declarations, Imports, Exports, Providers.

* Conhecendo os Arquivos do Projeto:
    - Por padrão o Angular usa o *TypeScript* e pra isso ele existe um arquivo de configuraçao **tsconfig.json** além desse tambem temos o arquivo angular.json que tambem é um arquivo de configuração e dentro dele faremos uma mudança... Em **inlineTemplete** mudar para *false* e **inlineStyle** também. Quando for criar os *componentes* o arquivo *html* e o arquivo de *estilo* estarão em arquivos separados. Quando deixamos como *inline* ele vai criar tudo em um arquivo só. Esta configuração é padrão quando instalamos o cli *minimal*.
    - Arquivo **main.ts**. Aqui irá importar algumas coisas, mais o mais importante que tem dentro dele, é que ele vai carregar, por padrão o que ele chamou de *AppModule*, ou seja, o míodulo da nossa aplicação.
    - Dentro da pasta **app**, onde temos o módulo criado, temos o arquivo de *routing*, *app.module* e o *component*.

* HTML do AppComponent:
    - Neste projeto não teremos templates *inline*, então, no arquivo *app.component* o templete pré configurado sera apagado. No lugar de template e style sera colocado uma variável chada app.component.htm e este arquivo será criado dentro desta pasta.
    - Observações: No arquivo *app.component* temos export class *AppComponent {title = 'frontend';}* e uma forma bacana de usar esta variavel no projeto é:
    No arquivo app.component.html, por exemplo:
    ```
        <h2>Olá, meu título é {{ title }}</h2>
    ```
    Essa sintaxe chamamos de *double mustache*. Quando envolvemos o nome da variável com *double mustache {{ variável }}* ele vai interpretar e substituir pelo valor.

* Instalar os Componentes do Material:
    - comando para instalar os componentes do *Material*:
        Na pasta do projeto (frontend)...
        ```
        ng add @angular/material
        ```
* Componente Cabeçalho:
    - Primeiramente criaremos o cabeçalho de forma simples. comando para instalar:
        ```
        ng g c components/template/header (g de generator e c de component)
        ```
    - Dentro do nosso app sera criado os seguintes arquivos...
        ```
        CREATE src/app/components/template/header/header.component.html (21 bytes)
        CREATE src/app/components/template/header/header.component.ts (275 bytes)
        CREATE src/app/components/template/header/header.component.css (0 bytes)
        ```
    - E vai atualizar o app.module.ts...
        ```
        UPDATE src/app/app.module.ts (604 bytes)
        ```
    - A partir disso o arquivo app.module.ts ficara assim...
        ```
            import { NgModule } from '@angular/core';
            import { BrowserModule } from '@angular/platform-browser';

            import { AppRoutingModule } from './app-routing.module';
            import { AppComponent } from './app.component';
            import { BrowserAnimationsModule } from '@angular/platform-browser/animations';
            import { HeaderComponent } from './components/template/header/header.component';

            @NgModule({
            declarations: [
                AppComponent,
                HeaderComponent
            ],
            imports: [
                BrowserModule,
                AppRoutingModule,
                BrowserAnimationsModule
            ],
            providers: [],
            bootstrap: [AppComponent]
            })
            export class AppModule { }
        ```
    - Em *app.component.html* podemos referenciar o header que foi criado. Existe um prefixo padrão para os componentes, ou seja, nossos componentes começam com o prefixo *app*. E como o nome do componente vai ser *header*, então usaremos...
        ```
        <app-header></app-header>
        ```
    - Criando um template para o *componente header*. Para inicar, precisamos importar a **ToolBar do Material** e para isso, ele vem de um módulo externo e iremos importar para nosso módulo *appModule*.
    Dentro de appModule.ts
    ```
    import { MatToolbarModule } from '@angular/material/toolbar';
    ```
    - Apos importar o *Toolbar* temos que colocar essa referência dentro de imports...
    ```
    imports: [
        BrowserModule,
        AppRoutingModule,
        BrowserAnimationsModule,
        MatToolbarModule <<<<<<
    ]
    ```
    - Agora podemos definir nosso template do header...
    ```
    (header.component.html)
    
    <mat-toolbar class="header mat-elevation-z4">
    <span>
        <a>
            <h2>Analy<span>Sys</span> </h2>
        </a>
    </span>
    <span class="title-group">
        <a>
            <i class="material-icons">
                home
            </i>
            Aplicação CRUD
        </a>
    </span>
    </mat-toolbar>

    (header.component.css)

    .header {
        display: flex;
        align-items: center;
    }

    .header a {
        display: flex;
        align-items: center;
        text-decoration: none;
    }

    .header a > h2 {
        font-size: 1.7rem;
        font-family: 'Audiowide', cursive;
    }

    .header a > h2 > span {
        color: #3f3f94;
    }

    .header .title-group {
        padding-left: 25px;
    }

    .header .title-group i {
        padding-right: 5px;
    }
    ```