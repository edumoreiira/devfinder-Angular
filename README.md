# DevFinder - Angular Edition

Este projeto é uma solução para o desafio "GitHub user search app" do [Frontend Mentor](https://www.frontendmentor.io/challenges/github-user-search-app-Q09YOgaH6), construído com **Angular**. A aplicação permite que os usuários pesquisem por perfis de usuários do GitHub e visualizem suas informações de forma clara e organizada.

O foco foi criar uma interface limpa, responsiva e funcional, aproveitando os recursos do ecossistema Angular para uma experiência de desenvolvimento moderna.

## 🚀 Live Demo

**Visualize o projeto em ação acessando o link do GitHub Pages:**

### **[https://edumoreiira.github.io/devfinder-Angular/](https://edumoreiira.github.io/devfinder-Angular/)**

## ✨ Funcionalidades

  - **Pesquisa de Usuários do GitHub:** Encontre qualquer usuário do GitHub pelo seu nome de usuário.
  - **Visualização de Perfil:** Exibe informações detalhadas do usuário, incluindo nome, bio, data de entrada, número de repositórios, seguidores e a quem ele segue.
  - **Links Sociais:** Mostra informações de localização, blog, Twitter e empresa, quando disponíveis.
  - **Tema Claro e Escuro:** Um seletor de tema permite alternar entre os modos de visualização para melhor conforto visual.
  - **Design Responsivo:** A interface se adapta a diferentes tamanhos de tela, de dispositivos móveis a desktops.
  - **Tratamento de Erros:** Exibe uma mensagem amigável quando um usuário não é encontrado.

## 💻 Tecnologias Utilizadas

  - **Angular 17**
  - **TypeScript**
  - **RxJS** para programação reativa e chamadas HTTP
  - **SCSS** para estilização avançada

## ⚙️ Instalação e Execução

Para executar o projeto localmente, siga os passos abaixo:

1.  **Clone o repositório:**

    ```bash
    git clone https://github.com/edumoreiira/devfinder-Angular.git
    ```

2.  **Navegue até o diretório do projeto:**

    ```bash
    cd devfinder-Angular
    ```

3.  **Instale as dependências:**

    ```bash
    npm install
    ```

4.  **Execute o servidor de desenvolvimento:**

    ```bash
    ng serve
    ```

    Acesse `http://localhost:4200/` no seu navegador. A aplicação será recarregada automaticamente se você alterar qualquer um dos arquivos de origem.

## 🤝 Boas Práticas e Destaques do Código

Este projeto implementa diversas boas práticas do desenvolvimento com Angular.

### Angular & RxJS

  * **Separação de Responsabilidades com Serviços:** A lógica para se comunicar com a API do GitHub está encapsulada no `GitHubSearchService`. Isso mantém o componente limpo e focado apenas na apresentação e interação com o usuário.
  * **Programação Reativa com Observables:** O estado do usuário é gerenciado por um `Observable` (`user$`). O template utiliza o `async` pipe para se inscrever e desinscrever automaticamente, o que é a maneira mais eficiente e segura de lidar com `Observables` no Angular, prevenindo *memory leaks*.
  * **Gerenciamento de Subscriptions:** A chamada HTTP utiliza o operador `take(1)` para garantir que a inscrição seja finalizada após a primeira resposta da API, uma prática recomendada para evitar múltiplas emissões indesejadas.
  * **Comunicação entre Componentes:** A funcionalidade de troca de tema é implementada com `@Input()` e `@Output()`, permitindo que o `GithubSearchComponent` comunique a mudança de estado para o componente pai (`AppComponent`).

### TypeScript, HTML & CSS

  * **Tipagem Forte:** Uma interface (`GitHubSearch`) foi criada para modelar a resposta da API, garantindo a segurança de tipos e o autocompletar durante o desenvolvimento.
  * **Two-Way Data Binding:** O `[(ngModel)]` é utilizado para vincular o campo de busca à propriedade `searchResponse` no componente, simplificando a captura da entrada do usuário.
  * **Estilização Dinâmica com `[ngClass]`:** A troca de temas é aplicada dinamicamente no `AppComponent` usando a diretiva `[ngClass]`, que adiciona a classe CSS correta (`dark-theme` ou `light-theme`) com base no estado da aplicação.
  * **Renderização Condicional:** O template utiliza `@if` (ou `*ngIf`) para renderizar condicionalmente elementos, como a mensagem de erro ou os dados do usuário, somente quando eles existem.
