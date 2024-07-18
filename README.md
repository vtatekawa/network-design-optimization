
# 📦 Network Design Optimization

Bem-vindo ao projeto **Network Design Optimization**! Este repositório contém um script em Python que utiliza a biblioteca `PuLP` para resolver um problema complexo de otimização da cadeia de suprimentos. Abaixo, você encontrará um guia abrangente sobre o que este script faz, como usá-lo e como estruturar seus dados de entrada. Vamos lá! 🚀

## 📚 Índice

- [Visão Geral](#visão-geral)
- [Descrição do Problema](#descrição-do-problema)
- [Estrutura dos Dados de Entrada](#estrutura-dos-dados-de-entrada)
- [Dependências](#dependências)
- [Uso](#uso)
- [Saída](#saída)
- [Contribuindo](#contribuindo)
- [Licença](#licença)

## 📋 Visão Geral

Este script utliza programação linear com a ajuda da biblioteca `PuLP` para resolver um problema classico de otimização de malha, escolhendo a melhores origens para atendimentos considerando o menor custo total. O objetivo é minimizar os custos totais de produção e transporte em uma rede de fábricas, produtos e clientes.

## 🔍 Descrição do Problema

O script visa:
1. **Minimizar o Custo Total:** Calcular as quantidades ótimas de produção e distribuição para minimizar os custos combinados de produção e envio.
2. **Satisfazer a Demanda:** Garantir que a demanda de cada produto por cada cliente seja atendida.
3. **Respeitar as Capacidades:** Assegurar que as capacidades de produção das fábricas não sejam excedidas.
4. **Cumprir os Lotes Mínimos:** Garantir que as quantidades de produção atendam aos requisitos de lote mínimo.

### 🏭 O Problema de Otimização

Dado de Exemplo:
- **10 fábricas**
- **100 SKUs (produtos)**
- **200 clientes**

os dados aqui são ficticios usados apenas para exemplo de como os dados reais devem ser inseridos nas planilhas de input.

O script define o seguinte:
- **Variáveis de Decisão:** Quantidades de produção para cada combinação de fábrica, produto e cliente.
- **Função Objetivo:** Minimizar o custo total, que inclui os custos de produção e transporte.
- **Restrições:** Restrições de capacidade de produção para cada fábrica, atendimento da demanda para cada cliente e lotes mínimos de produção.

## 📊 Estrutura dos Dados de Entrada

Para usar este script, você precisa preparar seus dados de entrada na pasta input conforme os exemplos lá existentes, após feito isso, a segundar parte do código no notebook irá transformar os dados da seguinte forma:

1. **Lista de Fábricas:** Uma lista com os nomes das fábricas.
2. **Lista de Produtos:** Uma lista com os nomes dos produtos.
3. **Lista de Clientes:** Uma lista com os nomes dos clientes.
4. **Custos de Produção:** Um dicionário com chaves como tuplas `(fábrica, produto)` e valores como custos de produção.
5. **Custos de Transporte:** Um dicionário com chaves como tuplas `(fábrica, cliente)` e valores como custos de transporte.
6. **Capacidades das Fábricas:** Um dicionário com os nomes das fábricas como chaves e suas capacidades de produção como valores.
7. **Demandas dos Clientes:** Um dicionário aninhado com os nomes dos clientes como chaves e dicionários de demandas de produtos como valores.
8. **Rendimentos de Produção:** Um dicionário com chaves como tuplas `(fábrica, produto)` e valores como taxas de rendimento.
9. **Lotes Mínimos:** Um dicionário com chaves como tuplas `(fábrica, produto)` e valores como tamanhos mínimos de lote de produção.

### Exemplo

```python
fabricas = ["Fabrica_1", "Fabrica_2", ..., "Fabrica_10"]
produtos = ["Produto_1", "Produto_2", ..., "Produto_100"]
clientes = ["Cliente_1", "Cliente_2", ..., "Cliente_1000"]

custos = {("Fabrica_1", "Produto_1"): 15.0, ...}
custo_frete = {("Fabrica_1", "Cliente_1"): 5.0, ...}
capacidade_fabricas = {"Fabrica_1": 5000, ...}
demanda_clientes = {"Cliente_1": {"Produto_1": 10, ...}, ...}
rendimento = {("Fabrica_1", "Produto_1"): 0.95, ...}
lote_minimo = {("Fabrica_1", "Produto_1"): 20, ...}
```

## 🛠 Dependências

Certifique-se de ter as seguintes dependências instaladas:

- Python 3.x
- PuLP
- Pandas

Instale-as usando pip:

```bash
pip install pulp pandas
```

## 🚀 Uso

1. Clone este repositório:

Apenas rode cada uma das celulas do notebook.

## 📈 Saída

Após executar o script, você obterá:

- **Status da Otimização:** Se a otimização foi bem-sucedida.
- **Custos Totais:** Custo total por fábrica e custos de produção otimizados gerais.
- **Resultados Detalhados:** Um DataFrame com resultados detalhados, incluindo quantidades de produção e custos para cada combinação fábrica-produto-cliente.

### Exemplo de Saída

```plaintext
Status da otimização: Ótimo
Custo total por fábrica:
Fabrica_1: 12345.67
...
Total Otimizado produzido por fábrica:
Fabrica_1: 5678.90
...
Resultados Detalhados:
```

Os resultados detalhados serão impressos e também podem ser exportados para um arquivo Excel na pasta output para análise posterior.

## 📄 Licença

Este projeto está licenciado sob a Licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

Feito com 🧠 por [Vitor Tatekawa](https://github.com/vtatekawa)
