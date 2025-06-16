# Atividade de Banco de Dados - Concessionária

## Objetivo

Modelar e implementar um banco de dados relacional para controlar os veículos, clientes, vendas e vendedores de uma concessionária.

---

## Parte 1 - Entendimento do Cenário

A concessionária **"AutoFácil"** vende veículos novos e usados. Cada venda envolve um cliente, um vendedor e um ou mais veículos. É necessário manter o registro dos clientes, veículos disponíveis, vendedores e as vendas realizadas.

---

## Parte 2 - Modelagem (Entidades e Relacionamentos)

### Tabelas:

- **Cliente**: (ID, Nome, CPF, Telefone)  
- **Vendedor**: (ID, Nome, Matrícula, Telefone)  
- **Veículo**: (ID, Modelo, Marca, Ano, Preço, Status)  
  - *Status:* "Disponível", "Vendido"
- **Venda**: (ID, ID_Cliente, ID_Vendedor, Data)  
- **ItemVenda**: (ID_Venda, ID_Veiculo)

**Desafio:**  
Crie um diagrama entidade-relacionamento (ER) representando essas tabelas e os relacionamentos entre elas.

---

## Parte 3 - Criação das Tabelas (SQL)

Escreva os comandos SQL para criar as tabelas conforme a modelagem acima. 

---

## Parte 4 - Inserção de Dados

Insira os seguintes dados fictícios no banco:

- **3 clientes**
- **2 vendedores**
- **10 veículos** (alguns com status "Disponível", outros "Vendido")
- **3 vendas** com respectivos itens vendidos

---

## Parte 5 - Consultas SQL

Crie comandos SQL para responder:

1. Liste todos os veículos disponíveis para venda.  
2. Liste todas as vendas realizadas com nome do cliente, nome do vendedor e data.  
3. Mostre os veículos vendidos em cada venda.  
4. Liste o total de vendas (valor) por vendedor.  
5. Mostre o total gasto por cada cliente.  
6. Liste os veículos que ainda não foram vendidos.

---

## Parte 6 - Entrega

1. Entregar arquivo projeto-concessionario.sql, com todos os comandos necessário para replicar toda a base e registros.

## Parte 7 - Reflexão

1. O que aconteceria se não usássemos a tabela `ItemVenda`?
2. Por que é importante manter o campo "Status" do veículo atualizado após uma venda?

---
