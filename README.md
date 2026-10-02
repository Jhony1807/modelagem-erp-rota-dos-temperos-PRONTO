# 🌿 ERP — Rota dos Temperos
> **Disciplina:** Modelagem de Banco de Dados  
> **Projeto:** Modelo Conceitual do Sistema ERP para Gestão de Temperos e Especiarias

---

## 👥 1. Identificação da Equipe

- Bruno Gomes Tibellio
- Erick Andrade de Peder
- Gabriel Marques Lopes
- Jônata Alves Borsari
- João Frazão Zanon
- Mateus de Lima Monteiro
- Murilo Domingues Saes
- Everton Santos Lima

---

## 🏬 2. Caracterização da Empresa

A **Rota dos Temperos** é um pequeno negócio familiar do segmento de comércio de temperos e especiarias. A empresa comercializa diferentes tipos de produtos relacionados, atendendo principalmente clientes da região.

Atualmente, o negócio possui processos relacionados a vendas, compras, estoque e controle financeiro. Grande parte dessas informações é controlada manualmente, o que dificulta a organização e o acompanhamento das operações.

### Principais Setores e Áreas Envolvidas
- Vendas e atendimento
- Estoque
- Compras e fornecedores
- Controle financeiro

### Principais Dados Utilizados
Clientes, funcionários, fornecedores, produtos, pedidos, compras, movimentações de estoque, contas a receber e contas a pagar.

---

## 🎯 3. Justificativa da Escolha do Negócio

A Rota dos Temperos foi escolhida por apresentar processos reais e estruturados que podem ser analisados e transformados em um modelo de dados.

O negócio apresenta problemas relacionados ao controle manual das informações, ausência de integração entre processos e dificuldade de acompanhamento de vendas, estoque e informações financeiras.

A empresa possui alto potencial para utilização de um sistema ERP, permitindo centralizar informações e integrar processos cruciais. Dessa forma, oferece um contexto adequado para a aplicação dos conceitos de modelagem de dados propostos na disciplina.

---

## ⚠️ 4. Problemas e Necessidades Identificados

| Problema Identificado | Consequência |
| :--- | :--- |
| **Controle realizado manualmente** | Dificulta o acompanhamento geral do negócio |
| **Controle de estoque manual** | Estoque desatualizado e risco de vender produtos sem disponibilidade |
| **Vendas não integradas ao estoque** | Diferença entre o controle e a quantidade realmente disponível |
| **Contas a pagar e a receber controladas separadamente** | Dificuldade para acompanhar valores financeiros |
| **Ausência de histórico organizado de fornecedores e preços** | Dificuldade para consultar compras anteriores e comparar valores |

Esses problemas demonstram a necessidade imediata de centralização, organização e integração das informações.

---

## 🔄 5. Principais Processos de Negócio

### 5.1 Processo de Venda
> Cliente escolhe os produtos ➔ Funcionário verifica estoque ➔ Produto disponível ➔ Pedido é registrado ➔ Estoque é atualizado ➔ Conta a receber é gerada.
> 
*Nota: Quando o produto não está disponível, o cliente é informado sobre a indisponibilidade.*

### 5.2 Processo de Compra
> Funcionário identifica a necessidade de reposição ➔ Ordem de compra é registrada ➔ Fornecedor realiza a entrega ➔ Produtos são conferidos ➔ Entrada no estoque é registrada ➔ Conta a pagar é gerada.
> 
*Nota: Quando os produtos entregues não conferem com o pedido, a divergência é registrada e o fornecedor é contatado.*

### 5.3 Processo de Estoque
O estoque é atualizado a partir das entradas provenientes das compras e das saídas geradas pelas vendas. As movimentações permitem acompanhar os produtos que entram e saem em tempo real.

### 5.4 Processo Financeiro
O sistema deve controlar as contas geradas pelas vendas e pelas compras, permitindo acompanhar valores, parcelas, vencimentos, pagamentos e situações em aberto ou atrasadas.

---

## ⚙️ 6. Requisitos Funcionais (RF)

- **RF01:** O sistema deverá cadastrar, editar e consultar clientes, funcionários, fornecedores e produtos.
- **RF02:** O sistema deverá registrar pedidos de venda com múltiplos produtos.
- **RF03:** O sistema deverá registrar ordens de compra de fornecedores com múltiplos produtos.
- **RF04:** O sistema deverá atualizar o estoque automaticamente a partir das vendas e compras realizadas.
- **RF05:** O sistema deverá gerar contas a receber a partir dos pedidos.
- **RF06:** O sistema deverá gerar contas a pagar a partir das ordens de compra.
- **RF07:** O sistema deverá gerar opções de pagamento conforme as regras do negócio.
- **RF08:** O sistema deverá permitir consultar o histórico de compras de cada cliente.

---

## 🛡️ 7. Requisitos Não Funcionais (RNF)

- **RNF01:** O sistema deverá ser acessado por navegador, sem necessidade de instalação local.
- **RNF02:** O sistema deverá controlar o acesso por perfil de usuário.
- **RNF03:** O sistema deverá manter registro (auditoria) das operações realizadas pelos usuários.
- **RNF04:** O sistema deverá apresentar as consultas em tempo adequado para utilização operacional.
- **RNF05:** O sistema deverá realizar backup periódico do banco de dados.

---

## 📏 8. Regras de Negócio / Operacionais

1. Um pedido/ordem de compra precisa possuir pelo menos um item.
2. O preço unitário em um pedido deve representar o preço praticado naquele momento (histórico de preço).
3. Toda venda deverá gerar uma movimentação de saída de estoque por item vendido.
4. Toda ordem de compra recebida deverá gerar uma movimentação de entrada de estoque por item comprado.
5. Uma pessoa pode exercer o papel de cliente, funcionário ou ambos, conforme o modelo adotado.
6. CPF e CNPJ devem ser identificadores únicos.
7. Cada pedido/ordem de compra deve possuir exatamente um funcionário responsável pelo registro.
8. Uma pessoa pode receber apenas um papel de cliente, funcionário ou ambos.
9. Uma conta a receber não deve possuir data de vencimento futura após o vencimento definido pelo pedido.
10. Um pedido pode não possuir cliente identificado quando se tratar de uma venda avulsa.
11. O pagamento de uma ordem de compra pode ocorrer de forma parcelada.

---

## 🔐 9. Restrições e Políticas Organizacionais

- O cancelamento de um pedido já registrado só poderá ser realizado pelo funcionário responsável ou pelo proprietário.
- O desconto acima do limite definido dependerá de aprovação superior.
- A compra com fornecedor deverá ser registrada mediante ordem de compra formal.
- O pagamento só deverá ser considerado realizado mediante confirmação efetiva do pagamento.
- Produtos sem estoque não deverão ser considerados disponíveis para venda.

---

## 📊 10. Fluxogramas

Os principais processos do negócio são representados por fluxogramas específicos:
- **Venda:** Do atendimento ao registro financeiro e baixa de estoque.
- **Compra:** Da necessidade de reposição à conferência de produtos e geração de contas a pagar.
- **Estoque:** Registro das movimentações de entrada e saída.
- **Financeiro:** Controle e baixa de contas a receber e pagar.

---

## 🏷️ 11. Entidades

- **`PESSOA`**: Representa os dados comuns de clientes e funcionários.
- **`CLIENTE`**: Representa a pessoa que realiza compras.
- **`FUNCIONARIO`**: Representa o funcionário que atende clientes e registra operações.
- **`FORNECEDOR`**: Representa quem fornece os temperos para a empresa.
- **`PRODUTO`**: Representa cada tempero ou produto comercializado.
- **`PEDIDO`**: Representa uma venda realizada.
- **`ORDEM_COMPRA`**: Representa uma compra realizada junto a um fornecedor.
- **`ITEM_PEDIDO`**: Representa os produtos presentes em um pedido.
- **`ITEM_ORDEM_COMPRA`**: Representa os produtos presentes em uma ordem de compra.
- **`MOVIMENTACAO_SAIDA`**: Representa a saída de estoque provocada por uma venda.
- **`MOVIMENTACAO_ENTRADA`**: Representa a entrada de estoque provocada por uma compra.
- **`CONTAS_A_RECEBER`**: Representa os valores que os clientes devem à empresa.
- **`CONTAS_A_PAGAR`**: Representa os valores que a empresa deve aos fornecedores.

---

## 📋 12. Atributos

Os atributos foram definidos para atender aos requisitos operacionais. Entre os principais estão:
- **Identificadores:** IDs, CPF, CNPJ, Razão Social.
- **Dados Pessoais/Contatos:** Nome, Telefone, E-mail, Endereço.
- **Dados Profissionais:** Cargo, Data de Admissão, Salário.
- **Dados do Produto:** Categoria, Unidade de Medida, Preço de Venda.
- **Transacionais:** Datas de Pedido e Compra, Status, Valores, Quantidades, Vencimentos e Pagamentos.

> O detalhamento completo dos atributos e suas respectivas regras encontra-se no **Dicionário de Dados Conceitual**.

---

## 🔗 13. Relacionamentos

- `PESSOA` **assume** `CLIENTE`
- `PESSOA` **assume** `FUNCIONARIO`
- `CLIENTE` **realiza** `PEDIDO`
- `FUNCIONARIO` **atende** `PEDIDO`
- `FUNCIONARIO` **registra** `ORDEM_COMPRA`
- `FORNECEDOR` **fornece** `ORDEM_COMPRA`
- `PEDIDO` **contém** `ITEM_PEDIDO`
- `PRODUTO` **é incluído em** `ITEM_PEDIDO`
- `ORDEM_COMPRA` **contém** `ITEM_ORDEM_COMPRA`
- `PRODUTO` **é adquirido em** `ITEM_ORDEM_COMPRA`
- `ITEM_PEDIDO` **gera** `MOVIMENTACAO_SAIDA`
- `ITEM_ORDEM_COMPRA` **gera** `MOVIMENTACAO_ENTRADA`
- `PEDIDO` **origina** `CONTAS_A_RECEBER`
- `ORDEM_COMPRA` **origina** `CONTAS_A_PAGAR`

---

## 🔢 14. Cardinalidades

As cardinalidades foram determinadas analisando os dois sentidos de cada relacionamento conforme as regras de negócio. O modelo apresenta relações `1:1`, `1:N` e entidades associativas para tratar as relações N:M entre pedidos/ordens de compra e seus produtos. As definições detalhadas estão representadas no **DER**.

---

## 📖 15. Dicionário de Dados Conceitual

O dicionário detalha **Entidade**, **Atributo**, **Descrição** e **Regra/Observação**, garantindo o alinhamento sobre o significado e finalidade de cada dado no modelo conceitual.

---

## 🎨 16. Diagrama Entidade-Relacionamento (DER)

O DER consolida a estrutura conceitual do ERP, reunindo entidades, atributos, relacionamentos, cardinalidades e restrições. Ele é o resultado direto da análise dos processos e requisitos do negócio.

---

## 💡 17. Justificativas Técnicas

- **Generalização/Especialização (`PESSOA`):** Concentra dados comuns a clientes e funcionários, garantindo reaproveitamento e evitando redundância.
- **Entidades Associativas (`ITEM_PEDIDO` / `ITEM_ORDEM_COMPRA`):** Permitem que um pedido ou ordem de compra possua múltiplos produtos com seus respetivos preços históricos e quantidades.
- **Movimentações de Estoque:** Separação explicita entre entradas e saídas para manter histórico auditável de alteração física de estoque.
- **Contas a Pagar / Receber:** Mapeamento independente das obrigações financeiras originadas pelas compras e vendas.

---

## 🏁 18. Conclusão

A modelagem desenvolvida para a Rota dos Temperos estrutura com clareza os processos operacionais do negócio em um modelo conceitual consistente. O resultado obtido estabelece uma base sólida para as próximas etapas do ciclo de vida do banco de dados: **modelo lógico, normalização, modelo físico e implementação**.
