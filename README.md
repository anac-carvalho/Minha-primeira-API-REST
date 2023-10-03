# Minha primeira API REST #

Neste projeto uma API REST que simula um Banco Digital. Essa aplicação foi desenvolvida como parte do desafio de fim Módulo 2 do curso de Desenvolvimento de Software - com foco em Backend - da Cubos Academy. 

Nessa API cosesguimos desenvolver uma variedade de funcionalidades para gerenciar contas bancárias. Trago elas descritas a seguir!

## Funcionalidades

-   Criação de conta bancária
-   Listagem das contas bancárias
-   Atualizar os dados do usuário da conta bancária
-   Excluir uma conta bancária
-   Depósitar em uma conta bancária
-   Sacar de uma conta bancária
-   Transferir valores entre as contas bancárias
-   Consultar saldo das contas bancárias
-   Emitir extrato bancário


## Estrutura do projeto

O código deste projeto está organizado da seguinte forma:

- `index.js`: Arquivo principal da aplicação;
- `rotas.js`: Arquivo de definição das rotas da API;
- Pasta `controladores`: Contém os controladores responsáveis por tratar as requisições;
- `bancodedados`: Arquivo que armazena os dados que são utilizados pela aplicação;
- `verificarSenhas`: Arquivo responsável por armazenar rotas de segurança das inforamções e transações de contas;

## Endpoints da API

### Listar contas bancárias
- Método: GET
- Rota: /contas
- Parâmetros: senha_banco - Senha do banco para autenticação
- Descrição: Lista todas as contas bancárias existentes.

### Criar conta bancária
- Método: POST
- Rota: /contas
- Descrição: Cria uma conta bancária, gerando um número único de identificação (numeroConta).

  ##### Exemplo de Requisição

```javascript
// POST /contas
{
    nome: "Ana Campos",
    cpf: "00011122235",
    data_nascimento: "1987-05-18",
    telefone: "11999999999",
    email: "ana@cubos.com",
    senha: "12345"
}
```

# Atualizar usuário da conta bancária
- Método: PUT
- Rota: /contas/:numeroConta/usuario
- Descrição: Atualiza os dados do usuário de uma conta bancária específica.

#### Exemplo de Requisição
```javascript
// PUT /contas/:numeroConta/usuario
{
    nome: "Ana Campos",
    cpf: "00011122235",
    data_nascimento: "1987-05-18",
    telefone: "11999999999",
    email: "ana@cubos.com",
    senha: "12345"
}
```

### Excluir Conta
- Método: DELETE
- Rota: /contas/:numeroConta
- Descrição: Exclui uma conta bancária existente.

### Depositar
- Método: POST
- Rota: /transacoes/depositar
- Descrição: Realiza um depósito em uma conta válida e registra a transação.

#### Exemplo de Requisição
```javascript
// POST /transacoes/depositar
{
	"numero_conta": "1",
	"valor": 1000
}
```

### Sacar
- Método: POST
- Rota: /transacoes/sacar
- Descrição: Realiza um saque em uma conta bancária e registra a transação.

##### Exemplo de Requisição
```javascript
// POST /transacoes/sacar
{
	"numero_conta": "1",
	"valor": 1000,
    "senha": "12345"
}
```

### Transferir
- Método: POST
- Rota: /transacoes/transferir
- Descrição: Permite a transferência de recursos entre contas bancárias e registra a transação.

#### Exemplo de Requisição
```javascript
// POST /transacoes/transferir
{
	"numero_conta_origem": "1",
	"numero_conta_destino": "2",
	"valor": 200,
	"senha": "123456"
}
```

### Saldo
- Método: GET
- Rota: /contas/saldo
- Parâmetros: numero_conta - Número da conta, senha - Senha do usuário
- Descrição: Retorna o saldo de uma conta bancária.

### Extrato
- Método: GET
- Rota: /contas/extrato
- Parâmetros: numero_conta - Número da conta, senha - Senha do usuário
- Descrição: Lista as transações realizadas em uma conta específica.


## Executando o Projeto
Para executar este projeto, siga os passos abaixo:

1. Clone este repositório.
2. Instale as dependências necessárias com o comando: npm install.
3. Inicie a aplicação com: `npm run dev`.

Este projeto foi desenvolvido em um contexto de aprendizagem, para o módulo 02, com foco em NOde.js do curso de Desenvolvimento de Software - Foco em Backend - da Cubos Academy, com o intuito de fornecer um exemplo de API REST para um Banco Digital. Sinta-se à vontade para utilizá-lo como base para seus próprios projetos ou estudos.

tags: `back-end` `módulo 2` `nodeJS` `API REST` `desafio` `Node.js`