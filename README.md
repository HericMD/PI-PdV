# Modelo - Padaria Pão Legal

Professores: Marco André Mendes e Alann Perini.

Equipe:
- Alison Manoel Raffaelly    
- Heric Matheus Damasio
- Marcus Vinícius de Oliveira  

Links do projeto: (Coloque aqui os links para a documentação do projeto e os repositórios e plubicação do backend e frontend.)

Documentação: https://github.com/HericMD/PI-PdV   
Backend: Repositório e Publicação  
Frontend: Repositório e Publicação  

# Situação Problema

A Padaria Pão Legal, do Sr. Genival, existe há 2 anos, e faz venda e entregas de pães, salgados e doces de alta qualidade. Recentemente ele contratou mais funcionários para atendimento de caixa, panificação, etc.

Devido ao rápido crescimento da empresa, faz-se necessária a instalação de um sistema de controle de vendas online que permita a criação e gerenciamento de contas e pedidos, ao caixa lançar as vendas realizadas e gerar relatórios de entrada e saída de produtos.

Foram descobertos problemas de organização com os pedidos feitos pelos clientes, então foi solicitado um sistema que organizasse seus pedidos, mostrando entrada e saída de produtos. Demandado pelo Sr. Genival, será feito um sistema que resolverá os problemas de gestão dentro da empresa "Padaria Pão Legal".

# Proposta

O sistema possuirá 4 níveis de acesso: clientes, entregadores, produção e gerente.  

- O cliente terá acesso aos produtos disponíveis para encomenda física na padaria ou entrega, carrinho de compras e gerenciar suas informações pessoais como endereço, forma de pagamento, etc.   
- O entregador terá acesso ao endereço de entrega do cliente para entrega.
- A produção terá acesso aos pedidos dos clientes para confecção dos produtos.  
- O gerente terá acesso aos relatórios de vendas e entregas mensais da padaria.  

O sistema funcionará da seguinte forma: o cliente cria um cadastro, faz o pedido, seleciona uma forma de pagamento e o tipo de entrega (retirada no local ou entrega a domicílio). Após pagamento ser efetuado, o pedido é liberado para ser feito pela produçao. Após finalizada a produção, os entregadores levam ou o cliente retira o pedido na padaria. 

Para um gerenciamento das vendas, serão gerados relatórios e consultas sobre as vendas, faturamento, etc. para os gerentes.

# Regras de negócio

**RN001 - Adição de Produtos:** O gerente deve adicionar os produtos que podem ser adicionados ao pedido. 

**RN002 - Produção:** Sempre são produzidos produtos para manter um estoque de pelo menos 5 e no máximo 50 de cada produto na padaria física;

**RN003 - Entrega do pedido:** O pedido só pode ser entregue em endereços na área definida pela padaria ou usar um padrão de área de 20km de raio, caso o endereço não cumpra esses requisitos, o pedido deve ser retirado no local físico;  

**RN004 - Criação de pedido:** Para criação de pedidos, o cliente deve estar cadastrado no sistema e os produtos disponíveis no sistema.  

**RN005 - Encaminhamento do pedido:**  Após o pedido ser efetuado, o mesmo pode ser visualizado pela equipe de produção;

**RN006 - Pagamento:** O método de pagamento pode ser selecionado ao adicionar o pedido, com pagamento na entrega ou na retirada com dinheiro, cartão de crédito, débito ou pix, ou pago previamente por cartão de crédito, débito ou pix;

**RN007 - Relatório:** Após qualquer venda os dados da venda são salvos, contendo produto vendido, faturamento e tempo gasto de entrega e produção para o dashboard do(s) gerente(s). 

# Requisitos Funcionais

## Entrada

**RF001 - Gerenciamento de clientes:** O sistema deve manter clientes;    
  **Dados necessários:** nome, login, senha, telefone e endereço.    
  **Usuários:** cliente.

**RF002 - Gerenciamento de funcionários:** O sistema deve manter funcionários;  
  **Dados necessários:** nome, login, senha, endereço, cpf, rg, carteira de trabalho e nível de permissão.  
  **Usuários:** produção e entregadores. 
  
**RF003 - Gerenciamento de produtos:** O sistema deve manter produtos;    
  **Dados necessários:** materias primas necessárias, tempo necessário para produção, valor de venda.   
  **Usuários:** gerente.  

## Processamento

**RF004 - Autenticação:** Todos usuários devem estar autenticados para usarem o sistema;    
  **Dados necessários:** cadastro, nível de permissão.    
  **Usuários:** todos níveis de usuário.

**RF005 - Gerenciamento de pedidos:** O sistema deve manter pedidos;  
  **Dados necessários:** produto(s), tipo de entrega, endereço, forma de pagamento, nível de permissão.  
  **Usuários:** clientes, produção e entrega.  

**RF006 - Pagamento:** O sistema deve permitir pagamentos com dinheiro físico, pix, cartão de crédito e débito;    
  **Dados necessários:** autenticação, conta em algum banco para pagamentos sem dinheiro físico.    
  **Usuários:** cliente.

## Saída

**RF007 - Gerenciamento de dados:** O sistema deve manter dados de estoque, venda, etc. para um dashboard;    
  **Dados necessários:** dados, autenticação.    
  **Usuários:** gerente.    

# Requisitos não funcionais

**RNF001 - Front-End:** o sistema será implementado com **VueJs**;  
**RNF002 - Back-End:** o sistema será implementado em **Django** com **DRF** e banco de dados **postgresql**;  
**RNF003 - Segurança de senha:** as senhas de usuários devem conter 8 ou mais caracteres, com pelo menos um número e uma letra;  
**RNF004 - Memória RAM:** é recomendado que o sistema possua no mínimo 4GB Ram para melhor performance;  
**RNF005 - Legislação:** o sistema deve seguir a legislação e LGPD;  
