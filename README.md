# sys_gmm_ipca

Script que realiza a coleta e regressão com dados em painel dinâmico (System GMM) do índice de inflação no Brasil (IPCA).

---

## Descrição

Este repositório contém um **notebook Jupyter** que realiza o processo de coleta, transformação e regressão de dados do **IPCA (Índice de Preços ao Consumidor Amplo)**, o principal indicador de inflação no Brasil. O objetivo é aplicar a metodologia **System GMM** para identificar as dinâmicas que influenciam o índice e gerar previsões baseadas nos resultados.

---

## Estrutura do Repositório

- `inflation.ipynb`: Notebook principal com todas as etapas do processo.
- `README.md`: Arquivo de documentação do repositório.

---

## Requisitos

Certifique-se de ter as seguintes dependências instaladas:

- Python 3.9 ou superior
- Bibliotecas:
  - `pandas`
  - `numpy`
  - `pydynpd`
  - `yfinance`
  - `requests`
  - `pyarrow` (para manipulação de arquivos Parquet)

---

## Etapas do Processo

### 1. Coleta e Transformação de Dados

- Os dados são obtidos de fontes públicas como:
  - **Banco Central do Brasil** (câmbio, saldo de crédito, taxa Selic, etc.).
  - **Yahoo Finance** (preços do petróleo Brent).
- As informações são integradas em um painel dinâmico adequado para análise.

### 2. Regressão System GMM

- Ajuste do modelo de painel dinâmico com a biblioteca `pydynpd`.
- Configuração de variáveis dependentes (IPCA) e independentes (indicadores econômicos).
- Validação do modelo com testes como:
  - **Teste de Hansen** (validação de instrumentos).
  - **Teste de Arellano-Bond** (verificação de correlação serial).

### 3. Previsão do IPCA

- Utiliza os coeficientes estimados para projetar a inflação do próximo período.
- A análise é feita considerando apenas coeficientes estatisticamente significativos.

---

## Contribuições

Contribuições são bem-vindas! Se você tiver sugestões, melhorias ou encontrar problemas, abra uma [issue](https://github.com/galvd/sys_gmm_ipca/issues) ou envie um pull request.

---

## Licença

Este projeto está licenciado sob a [MIT License](LICENSE).

---

## Autor

Desenvolvido por **[Daniel Galveas](https://github.com/galvd)**. Entre em contato para dúvidas ou colaborações!
