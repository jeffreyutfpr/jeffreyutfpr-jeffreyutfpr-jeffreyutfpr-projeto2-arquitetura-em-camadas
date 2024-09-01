# jeffreyutfpr-projeto2-arquitetura-em-camadas
Projeto 2 da disciplina "Arquitetura de Software - ES46A".

# Projeto 2 - Estudo de Caso: Análise e Proposta de Melhoria do MapOS

Nome: Jeffrey de Souza | RA: 1750895

**Código do sistema analisado**: [Repositório do MapOS no GitHub](https://github.com/RamonSilva20/mapos)

## 1. Introdução

Este projeto faz parte da disciplina de Arquitetura de Software ministrada pelo professor [Nome do Professor]. O objetivo é realizar um estudo de caso, documentação, e mapeamento de requisitos e processos do sistema MapOS, um software open-source desenvolvido no Brasil e utilizado principalmente por pequenas empresas e oficinas para gestão de ordens de serviço, controle de estoque e gestão de clientes.

O MapOS foi escolhido por sua arquitetura relativamente simples, mas suficientemente estruturada para um estudo detalhado. Além disso, sua popularidade e uso em produção por várias empresas brasileiras fornecem um contexto relevante para propor melhorias que possam ser aplicadas em ambientes reais.

## 2. Arquitetura do Sistema

O MapOS é um sistema web desenvolvido em PHP, que utiliza o padrão arquitetural MVC (Model-View-Controller). Abaixo, detalhamos cada uma das camadas e os principais módulos do sistema.

### 2.1 Tecnologias Utilizadas

- **Linguagem de Programação**: PHP
- **Frameworks**:
  - CodeIgniter (para estrutura MVC)
  - jQuery (para interações no frontend)
  - Bootstrap (para estilização e responsividade)
- **Banco de Dados**: MySQL
- **Servidor Web**: Apache

### 2.2 Camadas da Arquitetura

#### 2.2.1 Camada de Apresentação (View)

**Responsabilidades**: Esta camada é responsável pela interface com o usuário, renderizando as páginas web e gerenciando as interações.

- **Tecnologias**:
  - HTML, CSS, Bootstrap
  - JavaScript, jQuery
- **Principais Processos**:
  - Renderização de formulários de cadastro e consulta
  - Manipulação de eventos de usuário (cliques, validações)

#### 2.2.2 Camada de Lógica de Negócios (Controller)

**Responsabilidades**: Contém toda a lógica de negócios da aplicação, gerenciando as regras do sistema e a comunicação entre a interface do usuário e a camada de dados.

- **Tecnologias**:
  - PHP com CodeIgniter
- **Principais Processos**:
  - Validação de dados de entrada
  - Gerenciamento de ordens de serviço
  - Processamento de transações financeiras (faturamento)

#### 2.2.3 Camada de Persistência de Dados (Model)

**Responsabilidades**: Gerencia o acesso e a manipulação dos dados armazenados no banco de dados.

- **Tecnologias**:
  - MySQL (para armazenamento de dados)
  - Active Record (ORM do CodeIgniter)
- **Principais Processos**:
  - Criação, leitura, atualização e exclusão de registros no banco de dados
  - Mapeamento objeto-relacional dos dados

### 2.3 Módulos do Sistema

#### 2.3.1 Módulo de Gestão de Ordens de Serviço

**Descrição**: Gerencia todo o ciclo de vida das ordens de serviço, desde a criação até a finalização.

#### 2.3.2 Módulo de Gestão de Estoque

**Descrição**: Controle de entrada e saída de produtos, gerenciamento de inventário e alertas de estoque baixo.

#### 2.3.3 Módulo de Gestão de Clientes

**Descrição**: Gerenciamento de informações de clientes, histórico de ordens de serviço e comunicação.

## 3. Escalabilidade e Performance

O MapOS, como um sistema voltado para pequenas empresas, é projetado para ser leve e de fácil implantação. No entanto, há oportunidades para melhorias em escalabilidade e desempenho.

### 3.1 Escalabilidade Vertical

**Descrição**: O sistema pode ser escalado verticalmente através da alocação de mais recursos no servidor, como CPU e memória.

### 3.2 Escalabilidade Horizontal

**Descrição**: Implementar uma arquitetura que permita a replicação do servidor web e do banco de dados, distribuindo a carga entre múltiplas instâncias.

### 3.3 Cacheamento

**Descrição**: Uso de cache para dados frequentemente acessados, como listas de produtos ou clientes, para reduzir a carga no banco de dados.

### 3.4 Pooling de Conexões

**Descrição**: Implementação de pooling de conexões para otimizar o uso das conexões com o banco de dados, melhorando o tempo de resposta.

## 4. Propostas de Melhoria

### 4.1 Modernização da Interface (Frontend)

**Motivação**: Embora a interface do MapOS seja funcional, ela pode se beneficiar de uma modernização para melhorar a experiência do usuário.

**Proposta**: Migrar a interface para um framework mais moderno como React.js, que permite a criação de interfaces mais dinâmicas e responsivas. Além disso, utilizar técnicas de virtualização para melhorar o desempenho ao lidar com grandes volumes de dados.

### 4.2 Refatoração da Lógica de Negócios

**Motivação**: A lógica de negócios está acoplada diretamente aos controladores, o que pode dificultar a manutenção e a evolução do sistema.

**Proposta**: Refatorar a lógica de negócios para utilizar serviços desacoplados que possam ser testados e mantidos independentemente dos controladores.

### 4.3 Implementação de API RESTful

**Motivação**: Atualmente, a comunicação entre diferentes partes do sistema e possíveis integrações com outras aplicações são limitadas.

**Proposta**: Implementar uma API RESTful que permita a comunicação entre o MapOS e outras aplicações, facilitando a integração e a expansão do sistema.

## 5. Referências

- **Documentação Oficial do CodeIgniter**: [https://codeigniter.com/userguide3/](https://codeigniter.com/userguide3/)
- **Repositório do MapOS no GitHub**: [https://github.com/RamonSilva20/mapos](https://github.com/RamonSilva20/mapos)
- **Artigos sobre Modernização de Sistemas Legados**: [Link para Artigo](https://www.objective.com.br/insights/modernizacao-de-sistemas-legados/)
