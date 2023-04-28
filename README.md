Modelo 1 - Ponto de Vendas (PdV) 

**Introdução**  
A Padaria Pão legal :D do Sr Genival existe a 2 anos, e faz venda e entregas de pães, salgados e doces de alta qualidade. Recentemente ele contratou mais funcionários para atendimento de caixa, panificação, etc.

**Situação Problema**  
Devido o rápido crescimento da empresa, faz-se necessário a instalação de um sistema de controle de vendas que permita ao caixa lançar as vendas realizadas, e gerar relatórios.

**Conclusão**  
Foram descobertos problemas de organização com os pedidos feitos pelos clientes, então foi solicitado um sistema que organizasse seus pedidos, mostrando entrada e saída. Demandado pelo Sr. Genival, será feito um sistema que resolverá os problemas de gestão dentro da empresa "Padaria Pão Legal".

**Proposta**  
O foco do sistema será gerir vendas e gerar relatórios  
O sistema possuirá 3 níveis de acesso: clientes, funcionários, gerente.  
O cliente terá acesso aos produtos disponíveis, e para encomenda física na padaria, carrinho de compras e gerenciar suas informações pessoais como endereço, forma de pagamento, etc.  
O funcionário terá acesso aos relatórios de pedidos dos clientes e endereço de entrega.  
O gerente terá acesso aos relatórios de trabalho dos funcionários, e relatórios de vendas e entregas mensais da padaria.  

O sistema funcionará a partir do cliente criar um cadastro, fazer o pedido por um carrinho de compras, selecionar uma forma de pagamento, o pagamento ser efetuado, então é gerado um relatório para os funcionários padeiros/confeiteiros fazerem o pedido, e os funcionários fretistas levarem para entrega, também são gerados relatórios de vendas, gastos e horários de trabalho para os gerentes.

**Regras de negócio**

**RN001 - Criação de pedido:** Para criação de pedidos, o cliente deve estar cadastrado no sistema;  
**RN002 - Adicionar pedidos:** Para o atendimento se iniciar, o cliente precisa abrir um novo pedido;  
**RN003 - Encaminhamento do pedido:**  Para o pedido ser efetuado, a comanda deve ser cadastrada e mandada na mesma hora para os padeiros;  
**RN004 - Entrega do pedido:** Para começar uma entrega, o pedido deve ter um endereço e estar disponível para entrega;  
**RN005 - Pagamento:** O método de pagamento pode ser selecionado ao adicionar o pedido, com pagamento na entrega com dinheiro, cartão de crédito/débito ou pix, ou pago previamente por cartão de crédito, débito ou pix;  
**RN006 - Relatório:** Após qualquer venda é gerado um relatório contendo valor de venda e tempo gasto para os gerentes. 

**Requisitos Funcionais**

**RF001 - Gerenciamento de usuários:** O sistema deve manter usuários;  
  **Dados necessários:** login, senha, nível de permissão.  
  **Usuários:** todos níveis de usuário. 
  
**RF002 - Gerenciamento de produtos:** O sistema deve manter produtos;  
  **Dados necessários:** nível de permissão.  
  **Usuários:** gerente.  
  
**RF003 - Gerenciamento de pedidos:** O sistema deve manter pedidos;  
  **Dados necessários:** cadastro, nível de permissão.  
  **Usuários:** todos níveis de usuário.  
  
**RF004 - Carrinho:** O sistema deve possuir carrinho de compras;  
  **Dados necessários:** cadastro, nível de permissão.
  **Usuários:** todos níveis de usuário.
  
**RF005 - Gerenciamento de relatórios:** O sistema deve manter relatórios;
  **Dados necessários:** cadastro, nível de permissão.
  **Usuários:** funcionários e gerentes.

**RF006 - Pagamento:** O sistema deve permitir pagamentos com pix, cartão de crédito e débito;
  **Dados necessários:** cadastro, conta em algum banco, nível de permissão.
  **Usuários:** todos níveis de usuário.
  
**RF007 - Cálculo de impostos:** O sistema deve calcular os impostos a pagar automaticamente e ser adicionado ao valor dos pedidos;
  **Dados necessários:** pedidos
  **Usuários:** gerente.

**Requisitos não funcionais**

**RNF001 - Front-End:** o sistema será implementado com **Vue-Js**;  
**RNF002 - Back-End:** o sistema será implementado com banco de dados **Django**;  
**RNF003 - Segurança de senha:** as senhas de usuários devem conter 8 ou mais caracteres, com pelo menos um número e letra;  
**RNF004 - Memória RAM:** é recomendado que o sistema possua no mínimo 2GB Ram para melhor performance;  
**RNF005 - Legislação:** o sistema deve seguir a legislação e LGPD;  
