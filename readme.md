# 🏢 FEITOSA INVEST - Simulador de Fundos Imobiliários 📊

Este projeto é uma ferramenta construída no Excel com interface de aplicativo, desenvolvida para simular investimentos em Fundos Imobiliários (FIIs) de forma dinâmica. O objetivo é projetar o acúmulo de patrimônio e a geração de renda passiva (dividendos) com base em diferentes perfis de risco e estratégias de alocação.

## 🎯 As 5 Perguntas de Negócio Respondidas

A interface principal da ferramenta foi desenhada para responder de forma clara a cinco perguntas fundamentais logo na primeira tela:

1. **Quanto investir por mês?** (Configurado para utilizar 30% da renda, ex: R$ 1.500 de aporte para um salário de R$ 5.000).
2. **Por quantos anos?** (Campo de entrada editável, projetando cenários de longo prazo).
3. **Qual a taxa de rendimento mensal?** (Parâmetro ajustável, simulado a 1,08% ao mês).
4. **Quanto de patrimônio vai acumular?** (Cálculo dinâmico baseado nos aportes e juros compostos).
5. **Quanto vai receber de dividendos por mês?** (Estimativa de renda passiva mensal no fim do período).

## 🧮 Motores de Cálculo: Função VF e PROCV

Para dar vida à simulação e automatizar a montagem da carteira, utilizei duas lógicas avançadas do Excel:

* **Função VF (Valor Futuro):** Utilizada para projetar o **Patrimônio Acumulado**. A fórmula utiliza a taxa de rendimento mensal, o prazo convertido em meses (anos * 12) e o aporte mensal (como saída de caixa negativa). Isso permite ao Excel calcular o efeito dos juros compostos no longo prazo de forma exata.
* **Função PROCV com Chave Composta:** A distribuição do dinheiro entre os tipos de fundo muda dependendo do perfil do investidor. Para o Excel buscar a porcentagem correta, criei uma **chave composta** na aba de apoio unindo o perfil e o ativo com um hífen (ex: `Conservador-Papel` ou `Arrojado-Tijolo`). O PROCV lê o perfil selecionado, junta com o nome do fundo na linha correspondente, e traz o percentual exato de alocação em tempo real.

## 🏷️ Estruturação com Intervalos Nomeados

Para manter as fórmulas limpas, profissionais e fáceis de dar manutenção (sem depender de amarras como `$B$4`), mapeei as variáveis principais no Gerenciador de Nomes (Name Manager):
* `salario`
* `aporte`
* `prazo_anos`
* `taxa_mensal`
* `perfil_escolhido`

## 💼 Classes de Ativos e Estratégia de Alocação

A carteira do **Feitosa Invest** foi customizada para distribuir o capital entre 6 classes de fundos imobiliários: **Papel, Tijolo, Desenvolvimento, Hotelarias, FOFs e Híbrido**.

A planilha traz uma matriz de alocação personalizada. Como exemplo, a estratégia configurada para o **Perfil Arrojado** distribui o aporte mensal da seguinte forma:
* **Papel:** 50% (Foco em alto dividendo atrelado à inflação/CDI)
* **Desenvolvimento:** 20% (Maior risco focado em ganho de capital)
* **Tijolo:** 10% 
* **Hotelarias:** 10%
* **FOFs:** 5%
* **Híbrido:** 5%

*Nota: A planilha conta com uma trava de validação somando o total distribuído (ex: R$ 1.500) para garantir matematicamente que a alocação de qualquer perfil sempre feche em 100%.*

## 🚀 Diferenciais e Personalizações

Em relação ao modelo base do desafio, implementei as seguintes melhorias:
* **Identidade Visual:** Renomeação da ferramenta para "FEITOSA INVEST" com layout limpo, sem linhas de grade ou títulos de coluna.
* **Classes Exclusivas:** Adição de setores específicos como *Hotelarias*.
* **Aprimoramento de Busca:** Refatoração da chave composta do PROCV incluindo hifens (`-`) para melhor legibilidade dos dados na tabela de apoio.
* **Controle de Integridade:** Adição de uma linha de somatório para auditar financeiramente se o valor distribuído entre os fundos corresponde exatamente ao aporte informado.

## 📸 Telas da Aplicação
<img width="885" height="552" alt="Captura de tela 2026-10-29 174737" src="https://github.com/user-attachments/assets/303dc3f2-db22-44e8-9ddd-2609f8d664c9" />

