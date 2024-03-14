<h1 align="center"> 💠🏦Cubos-Bank</h1> 

#### O QUE É:
Este é um projeto de um Banco digital, uma implementação Backend de uma API Rest realizado como desafio do módulo 2 do curso desenvolvimento de sofware da Cubos Academy.

## DESCRIÇÃO DO PROJETO:
Este Banco realiza o cadastro, atualização, e deletar qualquer usuário, além disso é capaz de realizar todas as operações básicas de um Banco, são elas:
Depositar, sacar, transferir entre contas, conferir o saldo bancário, e  emitir o extrato bancário de uma determinada conta, todas estas funçoes estao com
suas validações de segurança, como por exemplo, ao sacar sempre séra pedido a senha para o usuário que estiver tentando sacar de uma determinada conta, além disso
um determinado funcionário do banco pode obter todas as contas cadastradas no banco, isso claro com a devida segurança passando uma senha de administração.

## DOCUMENTAÇÃO 

#### 📑package-lock.json
Arquivo onde está localizado os dados do projeto,  e as dependencias usadas.

#### 📁pasta src
Local onde está todos os arquivos e subpastas necessários para rodar o projeto. 

#### 📑bancodedados.json
Arquivo de memória, onde está gravado todas as informações do banco, todas as contas, e registro de operações como depositar, sacar e transferir.

#### 📑index.js
Arquivo principal responsavel por rodar todo o projeto.

#### 📑controller/BankControllers.js
Arquivo onde estar armazenada todas as funçôes callbacks responsaveis por tratar as requisições e as respostas do endpoint.

#### 📑controller/DataAccounts.js
Arquivo onde esta algumas funções auxiliares responsaveis por fazer o controle, verificação, função de ler e de escrever em arquivos.

#### 📑middleware/accountverifications.js
Arquivo que possui algumas funções de intermediário responsaveis por tratar o parametro de consulta.

#### 📑router/router.js
Arquivo onde está armazenada todas as rotas necessarias por realizar as funções e operações do Banco.

### ⤴️Detalhando os Endpoints

#### "/contas?senha_banco=Cubos123Bank"
Utilizando o verbo **GET** este endpoint é responsável por acessar e listar todas as contas cadastradas no banco, mas para isso uma senha deve ser passada. Cada conta na lista será um objeto possuindo as seguintes propriedades, os dados do usuário
(que terá um objeto com os dados pessoais do usuario), o saldo da conta, e o numero da conta(cada conta terá um número único e imutável.)  

#### "/contas"
Utilizando o verbo **POST** este endpoint é responsável por cadastrar novas contas no banco, ele recebe todos os campos preenchidos do corpo da requisição, e sao eles: nome, cpf, data de nascimento, telefone, email, e a senha, 
caso estes não forem preenchidos ou se algum campo estiver faltando, será retornada uma mensagem de erro. também será verificado se o número da conta, e o telefone são únicos no banco de dados, caso não for outra mensagem de erro será emitida.

#### "/contas/:numeroConta/usuario"
Com o verbo **PUT** este endpoint tem a função de atualizar os dados de uma conta, onde ele poderá atualizar qualquer dado, e se tentar colocar um CPF ou um email que está cadastrado em outra conta, uma mensagem de erro será retornada,
e também todos os dados deverão ser informados no corpo da requisição, ou um erro será emitido.

#### "/contas/:numeroConta"
Usando o verbo **DELETE** este endpoint tem a função de excluir uma conta informada como parametro de requisição, mas a exclusão da conta só será efetivada se o saldo da conta for zero, ou uma mensagem de erro será emitida.

#### "/transacoes/depositar"
Utilizando também o verbo **POST** este endpoint tem a função de realizar depósitos em uma determinada conta passando o numero da conta e o valor  a ser depositado no corpo da requisição, para isto o depósito nao pode ser zerado, e uma verificação de conta será feita
caso ela não exista uma mensagem de erro 404 será emitida, além disso, o numero da conta e o valor terá que ser informada, caso o deposito seja efetivado um registro do deposito será feito dentro do banco, contendo a data e hora do deposito, valor, e numero da conta

#### "/transacoes/sacar"
Com o verbo **POST** este endpoint tem a função de sacar um certo valor de uma conta, mas para ser executado a senha do usuário deverá também ser informada, além disso é impossivel sacar um valor maior que o saldo disponivel na conta, caso efetivado um registro do saque será gravado dentro do banco, também é obrigatório informar o numero da conta, valor e alem disso a senha, ou uma mensagem de erro será emitida, a conta informada deverá existir.

#### "/transacoes/transferir"
Este endpoint também usa o verbo **POST** e ele tem a função de realizar e registrar em seu banco de dados a transferência efetivada. Para uma transferência ser efetivada as contas de origem e destino devem ser informadas corretamente e caso elas não existam, uma mensagem de erro será retornada, a senha da conta de origem também deverá ser informada corretamente.

#### "/contas/saldo?numero_conta=123&senha=123"
A função de mostrar o saldo de uma determinada conta passada como parametro de consulta, fica a cargo deste endpoint que usa o verbo **GET**, para ser ter sucesso, e obter o retorno do saldo, a senha do usuario passada no parametro de consulta deverá estar correta, e é obrigatório ou  uma mensagem de erro será retornada, a função de verificação da senha e do numero da conta fica a cargo de um intermediario.

#### "/contas/extrato?numero_conta=123&senha=123"
Este endpoint usa o verbo **GET** e tem a função de emitir o extrato de uma conta, mostrando todas as transações da conta, depositos, saques, transferencias enviadas, transferencias recebidas, mas para isto a senha deverá ser informada e um intermediario irá verificar se a senha está correta, e se a conta existe.

## COMO EXECUTAR O PROJETO:
**Impotante:** O projeto ainda esta em sua fase inicial de desenvolvimento, então a unica maneira de executá-lo é  manualmente, através de um gerenciador de rotas como, o Insomnia, ou Postman.

**Passos para a execução do projeto**

- Acessando o repositório do projeto através deste link: <a target="_blank" href="https://github.com/giosobral/CubosBank">https://github.com/giosobral/CubosBank</a>
- Após isso deverá ser feito Clone do projeto dando o comando "Git Clone" atráves do terminal e colando a chave SSH ou o Link do repositorio.
- Dentro de um Editor de Código como por exemplo o VS Code, deverá dar o comando "npm install" para instalar todas as bibliotecas utilizadas no projeto
- Dê o Comando "npm run dev" no terminal, para iniciar o servidor
- Agora basta ir ate um gerenciador de rotas e Importar o Arquivo de coleção de requisições que está disponivel para download logo abaixo.
- Segue também o link de uma pasta no google drive com imagens de como importar uma coleção de requisições no insomnia, este arquivo é compativel com outros gerenciadores de rotas, como o Postman.

   ## 📥Download do Arquivo de coleções de requisição:
   - <a target="_blank" href="https://drive.google.com/file/d/1bD-D9McoB9SqMQhHdBad9O9U6XUNCT7S/view?usp=drive_link">CubosBank-API-Json</a>
    
   ## 🖼️Imagens:
  - <a target="_blank" href="https://drive.google.com/drive/folders/1E88j5APOVGH6xUAAsfxfZd9pV_pIrnkr?usp=drive_link">Importando uma Coleção de requisições para o insomnia</a>
  - <a target="_blank" href="https://drive.google.com/drive/folders/1M1qOER_-HD4b3HrGO83Cy26R8JxvmuWm?usp=drive_link">Prints do Projeto em funcionamento</a>

  






