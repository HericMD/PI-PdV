# Modelo - Padaria Pão Legal

Professores: 
- [Marco André Mendes](https://github.com/marrcandre)
- Alann Perini.

Equipe:
- Alison Manoel Raffaelly    
- [Heric Matheus Damasio](https://github.com/HericMD/)
- [Marcus Vinícius de Oliveira](https://github.com/marcus-voliveira)  

Links do projeto:

[Backend](https://github.com/HericMD/PadariaBackend)  
[Frontend](https://github.com/HericMD/PadariaLegal)  

# Situação Problema

A Padaria Pão Legal, gerenciada pelo Sr. Genival, tem dois anos de operação e se dedica à venda e entrega de pães, salgados e doces de alta qualidade. Recentemente, a equipe foi expandida para atender a demanda crescente.

Com o rápido crescimento da empresa, tornou-se essencial a implementação de um sistema de controle de vendas online. Este sistema deve permitir a criação e gerenciamento de contas e pedidos, além de possibilitar ao caixa lançar as vendas realizadas e gerar relatórios de entrada e saída de produtos.

Foi identificado um problema de organização com os pedidos feitos pelos clientes. Portanto, o Sr. Genival solicitou um sistema que organizasse esses pedidos, mostrando a entrada e saída de produtos. O objetivo é resolver os problemas de gestão na empresa "Padaria Pão Legal".

# Proposta

O sistema proposto terá 4 níveis de acesso: clientes, entregadores, produção e gerente.

- Os **clientes** poderão visualizar os produtos disponíveis para encomenda, gerenciar o carrinho de compras e suas informações pessoais, como endereço e forma de pagamento.
- Os **entregadores** terão acesso ao endereço de entrega do cliente.
- A **produção** terá acesso aos pedidos dos clientes para preparação dos produtos.
- O **gerente** terá acesso aos relatórios de vendas e entregas mensais da padaria.

O funcionamento do sistema será da seguinte maneira: o cliente cria um cadastro, faz o pedido, seleciona uma forma de pagamento e o tipo de entrega (retirada no local ou entrega a domicílio). Após o pagamento ser efetuado, o pedido é liberado para ser preparado pela produção. Quando a produção é concluída, os entregadores levam ou o cliente retira o pedido na padaria.

Para o gerenciamento das vendas, serão gerados relatórios e consultas sobre as vendas, faturamento, etc. para os gerentes.

# Regras de negócio

**`RN001 - Adição de Produtos`** O gerente deve adicionar os produtos que podem ser adicionados ao pedido. 

**`RN002 - Produção`** Sempre são produzidos produtos para manter um estoque de pelo menos 5 e no máximo 50 de cada produto na padaria física;

**`RN003 - Entrega do pedido`** O pedido só pode ser entregue em endereços na área definida pela padaria ou usar um padrão de área de 20km de raio, caso o endereço não cumpra esses requisitos, o pedido deve ser retirado no local físico;  

**`RN004 - Criação de pedido`** Para criação de pedidos, o cliente deve estar cadastrado no sistema e os produtos disponíveis no sistema.  

**`RN005 - Encaminhamento do pedido`**  Após o pedido ser efetuado, o mesmo pode ser visualizado pela equipe de produção;

**`RN006 - Pagamento`** O método de pagamento pode ser selecionado ao adicionar o pedido, com pagamento na entrega ou na retirada com dinheiro, cartão de crédito, débito ou pix, ou pago previamente por cartão de crédito, débito ou pix;

**`RN007 - Relatório`** Após qualquer venda os dados da venda são salvos, contendo produto vendido, faturamento e tempo gasto de entrega e produção para o dashboard do(s) gerente(s). 

# Requisitos Funcionais

## Entradas

**`RF001 - Gerenciamento de clientes`** O sistema deve manter clientes;    
  - **Dados necessários:** nome, login, senha, telefone e endereço.    
  - **Usuários:** cliente.

**`RF002 - Gerenciamento de funcionários`** O sistema deve manter funcionários;  
  - **Dados necessários:** nome, login, senha, endereço, cpf, rg, carteira de trabalho e nível de permissão.  
  - **Usuários:** produção e entregadores. 
  
**`RF003 - Gerenciamento de produtos`** O sistema deve manter produtos;    
  - **Dados necessários:** materias primas necessárias, tempo necessário para produção, valor de venda.   
  - **Usuários:** gerente.  

## Processamentos

**`RF004 - Autenticação`** Todos usuários devem estar autenticados para usarem o sistema;    
  - **Dados necessários:** cadastro, nível de permissão.    
  - **Usuários:** todos níveis de usuário.

**`RF005 - Gerenciamento de pedidos`** O sistema deve manter pedidos;  
  - **Dados necessários:** produto(s), tipo de entrega, endereço, forma de pagamento, nível de permissão.  
  - **Usuários:** clientes, produção e entrega.  

**`RF006 - Pagamento`** O sistema deve permitir pagamentos com dinheiro físico, pix, cartão de crédito e débito;    
  - **Dados necessários:** autenticação, conta em algum banco para pagamentos sem dinheiro físico.    
  - **Usuários:** cliente.

## Saídas

**`RF007 - Gerenciamento de dados`** O sistema deve manter dados de estoque, venda, etc. para um dashboard;    
  - **Dados necessários:** dados, autenticação.    
  - **Usuários:** gerente.    

# Requisitos não funcionais

**`RNF001 - Front-End`** o sistema será implementado com **VueJs**;  
**`RNF002 - Back-End`** o sistema será implementado em **Django** com **DRF** e banco de dados **postgresql**;  
**`RNF003 - Segurança de senha`** as senhas de usuários devem conter 8 ou mais caracteres, com pelo menos um número e uma letra;  
**`RNF004 - Memória RAM`** é recomendado que o sistema possua no mínimo 4GB Ram para melhor performance;  
**`RNF005 - Legislação`** o sistema deve seguir a legislação e LGPD;  
