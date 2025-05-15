

# Boilerplate MVC em Node.js com PostgreSQL

Este projeto é um boilerplate básico para uma aplicação Node.js seguindo o padrão MVC (Model-View-Controller), utilizando PostgreSQL como banco de dados.

## Aula 05 - Como é o funcionamento do models, controller e endpoints no projeto em 15/05/2025? 

### Models:
&nbsp;&nbsp;&nbsp;&nbsp;No momento os models aluno, curso e professor fazem requisições, buscas e outras atividades no banco de dados (PostgreSQL com Supabase) como: No models de aluno o método findAllComCurso realiza um left join que busca os alunos referenciados com um dos cursos criados e retorna o resultado para o alunoController em rows.

### Controller:
&nbsp;&nbsp;&nbsp;&nbsp;Os controllers estão recebendo requisições por advindas de métodos HTTP em routes e declaram essa requisições em funções assincronas que recebem como parâmetro req e res (requisição e resposta). No mais com a informação do método HTTP o controller extrai os atributos que irá necessitar e os envia como parâmetro para o models, aguardando sua resposta para prosseguir e solicitar renderização em view. 

### Endpoints:
&nbsp;&nbsp;&nbsp;&nbsp;Os endpoints são criados em routes a partir dos métodos HTTP como post, get, render e controlam o sistema por meio da definição do path e do middleware ou função controladora. A sua criação se da por meio de uma instância do objeto router de Express seguido de um método http que esperam um path seguido de uma função. Dessa forma é atribuida uma relação em que no momento em que aquele path for utilizado o método http especificado será requisitado, tal qual a enviará para o controller listado. Também existem rotas com parâmetros dinâmicos para que o método seja aplicado de forma controlada, seja por Id, nome ou outros atributos. 

## Requisitos

- Node.js (versão X.X.X)
- PostgreSQL (versão X.X.X)

## Instalação

1. **Clonar o repositório:**

```bash
   git clone https://github.com/seu-usuario/seu-projeto.git
   cd seu-projeto
```

2. **Instalar as dependências:**
    
```bash
npm install
```
    
3. **Configurar o arquivo `.env`:**
    
Renomeie o arquivo `.env.example` para `.env` e configure as variáveis de ambiente necessárias, como as configurações do banco de dados PostgreSQL.
    

Configuração do Banco de Dados
------------------------------

1. **Criar banco de dados:**
    
    Crie um banco de dados PostgreSQL com o nome especificado no seu arquivo `.env`.
    
2. **Executar o script SQL de inicialização:**
    
```bash
npm run init-db
```
    
Isso criará a tabela `users` no seu banco de dados PostgreSQL com UUID como chave primária e inserirá alguns registros de exemplo.
    

Funcionalidades
---------------

* **Padrão MVC:** Estrutura organizada em Model, View e Controller.
* **PostgreSQL:** Banco de dados relacional utilizado para persistência dos dados.
* **UUID:** Utilização de UUID como chave primária na tabela `users`.
* **Scripts com `nodemon`:** Utilização do `nodemon` para reiniciar automaticamente o servidor após alterações no código.
* **Testes:** Inclui estrutura básica para testes automatizados.

Scripts Disponíveis
-------------------

* `npm start`: Inicia o servidor Node.js.
* `npm run dev`: Inicia o servidor com `nodemon`, reiniciando automaticamente após alterações no código.
* `npm run test`: Executa os testes automatizados.
* `npm run test:coverage`: Executa os testes e gera um relatório de cobertura de código.

Estrutura de Diretórios
-----------------------

* **`config/`**: Configurações do banco de dados e outras configurações do projeto.
* **`controllers/`**: Controladores da aplicação (lógica de negócio).
* **`models/`**: Modelos da aplicação (definições de dados e interações com o banco de dados).
* **`routes/`**: Rotas da aplicação.
* **`tests/`**: Testes automatizados.
* **`views/`**: Views da aplicação (se aplicável).

Contribuição
------------

Contribuições são bem-vindas! Sinta-se à vontade para abrir um issue ou enviar um pull request.

Licença
-------

Este projeto está licenciado sob a Licença MIT.

Este README.md fornece uma visão geral clara do boilerplate, incluindo instruções de instalação, configuração do banco de dados, funcionalidades principais, scripts disponíveis, estrutura de diretórios, como contribuir e informações de licença. Certifique-se de personalizar as seções com detalhes específicos do seu projeto conforme necessário.