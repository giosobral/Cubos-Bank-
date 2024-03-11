<h1 align="center"> 💠🏦Cubos-Bank</h1> 

#### O QUE É:
Este é um projeto de um Banco digital, uma implementação Backend de uma API Rest realizado como desafio do módulo 2 do curso desenvolvimento de sofware da Cubos Academy.

## DESCRIÇÃO DO PROJETO:
Este Banco realiza o cadastro, atualização, e deletar qualquer usuário, além disso é capaz de realizar todas as operações básicas de um Banco, são elas:
Depositar, sacar, transferir entre contas, conferir o saldo bancário, e  emitir o extrato bancário de uma determinada conta, todas estas funçoes estao com
suas validações de segurança, como por exemplo, ao sacar sempre séra pedido a senha para o usuário que estiver tentando sacar de uma determinada conta, além disso
um determinado funcionário do banco pode obter todas as contas cadastradas no banco, isso claro com a devida segurança passando uma senha de administração.

## COMO EXECUTAR O PROJETO:
**Impotante:** O projeto ainda esta em sua fase inicial de desenvolvimento, então a unica maneira de executá-lo é  manualmente, através de um gerenciador de rotas como, o Insomnia, ou Postman.

**Passos para a execução do projeto**

- Acessando o repositório do projeto através deste link: <a target="_blank" href="https://github.com/giosobral/desafio-backend-m2-t15">https://github.com/giosobral/desafio-backend-m2-t15</a>
- Após isso deverá ser feito Clone do projeto dando o comando "Git Clone" atráves do terminal e colando a chave SSH ou o Link do repositorio.
- Dentro de um Editor de Código como por exemplo o VS Code, deverá instalar umas bibliotecas com o comando "npm install", e passando o nome das bibliotecas que são: express, data-fns, poderás também instalar o nodemon, mas essa é opcional.
- Dê o Comando "node .src/index.js" no terminal
- Agora basta ir ate um gerenciador de rotas e criar as requisições passando as seguintes rotas para cada função do banco:

   ```javascript
   "OBS: O 'N' passado como parametro de requisição em algumas rotas significa o numero da conta, no caso vc deverá substituir este por um número"

  // LISTAR TODAS AS CONTAS CADASTRADAS NO BANCO: Verbo: GET Rota:localhost:3000/contas?senha_banco=Cubos123Bank
  // CADASTRAR UMA NOVA CONTA : Verbo: POST Rota:localhost:3000/contas
  // ATUALIZAR OS DADOS DE UMA CONTA: Verbo: POST Rota:localhost:3000/contas/N/usuario 
  // EXCLUIR UMA CONTA: Verbo: DELETE Rota:localhost:3000/contas/N
  // DEPOSITAR EM UMA CONTA: Verbo: POST Rota:localhost:3000/transacoes/depositar
  // SACAR DE UMA CONTA: Verbo: POST Rota:localhost:3000/transacoes/sacar
  // TRANSFERIR ENTRE CONTAS: Verbo: POST Rota:localhost:3000/transacoes/transferir
  // OBTER O SALDO DE UMA CONTA: Verbo: GET Rota:http://localhost:3000/contas/saldo?numero_conta=1&senha=12345
  // EMITIR O EXTRATO DE UMA CONTA: Verbo: GET Rota:http://localhost:3000/contas/saldo?numero_conta=1&senha=12345

   "OBS: a senha passada como  parametro de consulta é a senha do usuario informado pelo numero da conta, já a senha_banco é a senha administrativa do banco"
  ``` 






