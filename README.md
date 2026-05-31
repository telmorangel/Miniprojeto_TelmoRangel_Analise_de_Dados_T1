## README

# Mini-Projeto Avaliativo: Análise Exploratória de Dados no Varejo

> **Curso:** Análise de Dados com Python [T1] — Módulo 1 (Semana 07)
> **Estudante:** Telmo Rangel
> **Turma:** Analise_de_Dados_T1
> **Prazo de Entrega:** 01/06/2026 às 12h

## Descrição 🛒📊

Este projeto é uma atividade avaliativa proposta pela disciplina Análise de Dados, do curso da SCTEC Análise de Dados com Python e SQL e consiste em uma Análise Exploratória de Dados (AED) aplicada a uma base real de varejo, cujo objetivo é transformar dados brutos em informações operacionais úteis. O script aborda a extração, limpeza, formatação, e geração de estatísticas descritivas usando Python e a biblioteca Pandas.

## 🚀 Como Executar o Projeto

1. Este projeto foi construido dentro do Google Colab e pode ser acessado por este link :[https://colab.research.google.com/drive/1lfc5upVOfjiYHwSoZP9UetWMmvFdCjBs?usp=sharing](https://colab.research.google.com/drive/1lfc5upVOfjiYHwSoZP9UetWMmvFdCjBs?usp=sharing)
2. Outra forma de acesso é clonar este repositório ou downloader do arquivo `.py` / `.ipynb`.
3. Abra o arquivo no **Google Colab** ou **VSCode** (certifique-se de ter a extensão do Jupyter instalada).
4. Execute as células (ou o script completo) sequencialmente. O download da base de dados será feito automaticamente através da API do Kaggle na primeira célula.

## 💡 Principais Insights e Conclusões

Com base nas etapas de limpeza e análise descritiva desenvolvidas neste projeto, observamos que:

1. **Auditoria e Limpeza de Dados:** Registros corrompidos ('#N/D', strings de espaços em branco) e uma coluna fantasma ('Unnamed') foram localizados e removidos, garantindo a integridade dos dados.
2. **Qualidade de Dados (Duplicatas):** A base original possuía 96.553 registros 100% duplicados. Sua remoção reduziu o dataset de 830.000 para 733.447 entradas, mitigando distorções analíticas e garantindo unicidade.
3. **Tipagem de Dados Estratégica:** Colunas como 'DATA', 'CL_ID', 'CL_EC', 'CL_FHL' e 'PR_ID' foram convertidas para seus tipos apropriados (datetime, int64), viabilizando análises temporais e quantitativas precisas. O uso de `errors='coerce'` garantiu a robustez da conversão.
4. **Mapeamento e Legibilidade:** O estado civil ('CL_EC') foi mapeado de códigos numéricos para descrições textuais ('CL_ESTADO_CIVIL'), aprimorando a legibilidade e interpretação dos dados demográficos dos clientes.
5. **Higienização de Produtos:** Nulos e inconsistências ('#N/D', strings vazias) nas colunas 'PR_CAT' e 'PR_NOME' foram unificados sob rótulos como 'Sem Categoria' e 'Sem Nome', padronizando a categorização de produtos.
6. **Resolução de Inconsistências PR_NOME/PR_ID:** Identificou-se que 109 nomes de produtos estavam associados a múltiplos PR_ID's. A criação da coluna 'PR_NOME_SEGMENTADO' resolveu essa ambiguidade, permitindo a identificação unívoca de cada variação de produto.
7. **Comportamento de Compra por Gênero:** Clientes do gênero feminino ('F') apresentaram um volume de compras ligeiramente superior ao masculino ('M'), sugerindo oportunidades para campanhas de marketing segmentadas.
8. **Padrões de Compra por Segmento:** O segmento de clientes 'B' demonstrou o maior volume de compras, indicando ser o principal target demográfico da empresa.
9. **Perfil de Compra por Estado Civil:** Clientes 'Separados' e 'Solteiros' lideraram em volume de compras, seguidos por 'Divorciados' e 'Casado ou união estável', com 'Viúvos' representando a menor parcela.
10. **Comportamento do Consumidor (Número de Filhos):** A análise da coluna 'CL_FHL' revelou que a maioria dos clientes (moda e mediana 0) não possui filhos ou tem um número baixo (média de 1.15, 75% dos clientes com até 2 filhos). Isso sugere que estratégias de marketing focadas em famílias grandes podem precisar de um nicho específico.
11. **Validação da Regra de Negócio (CO_ID):** A análise confirmou que a vasta maioria das compras (aproximadamente 98.8%) contém múltiplos itens, validando 'CO_ID' como identificador de cupom fiscal ou transação que agrega diversos produtos.

## 💾 Dataset Limpo Gerado

Ao final da execução do projeto, um novo arquivo CSV, `Varejo_Limpo_Final.csv`, é gerado com todos os dados tratados e higienizados, pronto para futuras análises ou para uso em modelos de Machine Learning.
