# Partidos e Deputados - Projeto de Consumo de API da Câmara

Este projeto é uma aplicação web simples que faz parte da selação de desenvolvedores IFINET. A aplicação consome as APIs públicas da Câmara dos Deputados do Brasil para exibir uma lista de partidos e, ao selecionar um partido, exibir a lista de deputados vinculados a ele.

## Funcionalidades

- Exibir uma lista de partidos políticos, ordenados pela sigla.
- Ao clicar em um partido, exibir os detalhes do partido selecionado.
- Ao clicar no botão "Ver Deputados", exibir a lista de deputados associados ao partido selecionado.


## Tecnologias Utilizadas

- **HTML5**: Estrutura básica da página web.
- **CSS3**: Estilização simples para layout e design.
- **JavaScript (ES6)**: Responsável por interagir com a API e manipular o DOM.
- **API da Câmara dos Deputados**: Utilizada para obter informações dos partidos e deputados.

## Estrutura do Projeto

- `index.html`: Página principal que contém a estrutura da aplicação, estilização de pagina e scripts.


## Fluxo da Aplicação

1. **Carregamento da Página**: 
   - Ao carregar a página, a função `fetchPartidos()` é executada, fazendo uma chamada à API dos partidos para obter todos os partidos cadastrados.
   - Esses partidos são exibidos em uma lista (`<ul id="partido-list">`).

2. **Seleção de um Partido**:
   - Ao clicar em um item da lista de partidos, as informações do partido selecionado (nome e ID) são exibidas na área de detalhes.
   - Um botão "Ver Deputados" é disponibilizado, permitindo ao usuário consultar os deputados vinculados ao partido.

3. **Visualização de Deputados**:
   - Quando o usuário clica em "Ver Deputados", a função `fetchDeputados()` é chamada. Ela faz uma requisição à API de deputados passando a sigla do partido selecionado.
   - A lista de deputados é exibida abaixo da área de detalhes.
   - Caso o usuário selecione um novo partido, a lista de deputados é limpa antes de exibir a nova pesquisa.

## API Utilizadas

1. **API dos Partidos**: 
   - URL Base: `https://dadosabertos.camara.leg.br/api/v2/partidos`
   - Parâmetros usados: `ordem=ASC&ordenarPor=sigla`

2. **API dos Deputados**:
   - URL Base: `https://dadosabertos.camara.leg.br/api/v2/deputados`
   - Parâmetros usados: `ordem=ASC&ordenarPor=nome&siglaPartido={SIGLA}`

## Como Executar o Projeto

1. Clone o repositório:
    ```bash
    git clone https://github.com/seu-usuario/partidos-deputados.git
    ```

2. Abra o arquivo `index.html` no navegador.

3. A aplicação irá carregar a lista de partidos automaticamente. Clique em qualquer partido para ver os detalhes e, em seguida, clique em "Ver Deputados" para visualizar os deputados associados.



