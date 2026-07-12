# Simulador de Patrimônio & Matriz de Alocação (FIIs) 📈

Este repositório contém a documentação e instruções de uso para a planilha de planejamento financeiro e alocação estratégica de Fundos Imobiliários. A ferramenta foi projetada para calcular projeções de juros compostos baseadas em aportes mensais e definir a distribuição ideal de ativos por perfil de investidor.

---

## 📌 Sumário
1. [Visão Geral](#-visão-geral)
2. [Estrutura do Arquivo (Abas)](#-estrutura-do-arquivo-abas)
3. [Como Utilizar o Simulador](#-como-utilizar-o-simulador)
4. [Entendendo a Matriz de Alocação](#-entendendo-a-matriz-de-alocação)
5. [Premissas e Cálculos](#-premissas-e-cálculos)

---

## 📊 Visão Geral

A planilha divide-se em duas inteligências complementares:
1. **Planejamento de Curto/Longo Prazo:** Uma calculadora de cenários futuros baseada no salário atual, capacidade de poupança e taxas estimadas de dividendo.
2. **Estratégia de Portfólio:** Uma matriz detalhada de *Asset Allocation* focada em Fundos Imobiliários (FIIs), segmentando o peso ideal de cada segmento (Papel, Tijolo, Híbrido, FOFs) dependendo do nível de tolerância a risco.

---

## 🗂️ Estrutura do Arquivo (Abas)

### 1. ⚙️ Planilha1 (Configurações e Cenários)
Focada em simulações financeiras e projeção de crescimento do patrimônio líquido.
* **Bloco Configurações:** Define o Salário base, a Taxa de Rendimento esperada e calcula automaticamente a sugestão de investimento padrão (fixada em 30% do salário).
* **Bloco Investimento Mensal:** Onde se definem o valor real a ser aportado, o horizonte de tempo (anos) e calcula-se a estimativa do **Patrimônio Acumulado** final e do valor previsto para **Dividendos Mensais**.
* **Bloco Cenários:** Projeção temporal comparativa simulando metas automáticas para **2, 5, 10 e 20 anos**, exibindo simultaneamente o patrimônio acumulado e o retorno em dividendos para cada período.

### 2. 🎯 Planilha2 (Matriz de Perfil / Chave Composta)
Onde reside a inteligência estratégica de alocação de ativos em Fundos Imobiliários.
* **Mapeamento por Chave Composta:** Organiza as alocações usando identificadores únicos combinando o Perfil e o Segmento do fundo (Ex: `Conservador-PAPEL`, `Moderado-TIJOLO`, `Agressivo-DESENVOLVIMENTO`).
* **Pesos Estratégicos:** Define as fatias percentuais (%) recomendadas para cada perfil, permitindo o uso de fórmulas como `PROCV` ou `XLOOKUP` em carteiras reais com base no perfil escolhido.

---

## 🛠️ Como Utilizar o Simulador

Para simular o seu futuro financeiro na **Planilha1**, altere apenas as variáveis de entrada:

1. Inserir o valor do seu **Salário** e quanto deseja aplicar (**Quanto investir por mês**).
2. Definir a expectativa de **Taxa de rendimento mensal** (Ex: `0.01079` para ~1.08%).
3. Consultar a tabela inferior (**Cenários**) para obter respostas imediatas de quanto você acumulará nos marcos de tempo tradicionais e qual será sua renda passiva.

---

## 📐 Entendendo a Matriz de Alocação (FIIs)

A distribuição sugerida na **Planilha2** equilibra o risco entre setores mais estáveis (Tijolo) e setores de maior rendimento/risco (Papel, FOFs, Desenvolvimento):

| Perfil | Tipo de FII | % Sugerido | Objetivo Principal |
| :--- | :--- | :--- | :--- |
| **Conservador** | Papel / Tijolo | Alto Peso (30% / 50%) | Mitigar volatilidade e focar em fundos consolidados de tijolo e recebíveis de baixo risco. |
| **Moderado** | Diversificado | Pesos Equilibrados | Introdução de fatias em FOFs, Hotéis e Desenvolvimento (até 10% cada) para ganho de capital. |
| **Agressivo** | Papel / Oportunidades | Alocação Dinâmica | Maior exposição a risco de crédito (Papel) e projetos em fase inicial de desenvolvimento. |

---

## 💡 Melhores Práticas

* **Não sobrescreva as células de cálculo:** Na tabela de *Cenários*, os valores de patrimônio e dividendos utilizam fórmulas matemáticas de juros compostos. Altere apenas os valores da seção de parâmetros.
* **Uso de Chaves Compostas:** A coluna `CHAVE COMPOSTA` da Planilha2 serve como uma excelente base de dados para alimentar outras planilhas através da função `=PROCV(Perfil&"-"&Tipo; Planilha2!A:D; 4; FALSO)`.

---
*Planilha desenvolvida para fins de simulação e suporte educacional à gestão patrimonial.* 🚀
