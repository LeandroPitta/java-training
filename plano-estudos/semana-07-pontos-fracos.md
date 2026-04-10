# Semana 07 - Correcao de pontos fracos

## Objetivo

Atacar diretamente os temas com pior desempenho nos simulados e consolidar padroes de resolucao.

## Revisao do tema

Revisao orientada por dados (seu historico):

- Levantar top 10 erros: use frequencia para priorizar o que mais te derruba. Exemplo: se "off-by-one" apareceu 4x, ele vira foco da semana.
- Separar por causa raiz: descobrir "por que" evita tratar apenas sintoma. Exemplo: erro de logica pode nascer de leitura ruim do enunciado.
- Mapear padrao por tras do erro: conecte problema ao tema real. Exemplo: falha em substring recorrente indica lacuna em janela deslizante.
- Definir contramedida objetiva: cada erro precisa de acao verificavel. Exemplo: "antes de codar, escrever 3 casos de borda".

Modelo de causa raiz:

- "Errei porque nao entendi o enunciado" -> reescrever entrada/saida antes de codar.
- "Errei por borda" -> criar testes de limite antes da implementacao.
- "Errei por tempo" -> limitar tentativa inicial em 12-15 min.

## Checklist diario (5 dias)

- [ ] Dia 1: lista de erros top 10 + plano de ataque
- [ ] Dia 2: 4 questoes do tema mais fraco
- [ ] Dia 3: 4 questoes do segundo tema mais fraco
- [ ] Dia 4: 3 questoes mistas + 1 simulado curto
- [ ] Dia 5: simulado medio + revisao profunda

## Exercicios praticos tipo selecao

Escolha com base no seu historico:

- Tema A (mais fraco): 6-8 questoes com repeticao de padrao. Exemplo: se falha em janela, focar em substring/subarray.
- Tema B (segundo mais fraco): 6-8 questoes de consolidacao. Exemplo: combinar hash com duas pontas.
- Tema C (manutencao): 4 questoes para nao perder ritmo. Exemplo: 2 easy + 2 medium de temas fortes.

Formato recomendado para cada tema:

- 2 questoes easy de reforco: corrige erros basicos rapidamente. Exemplo: alvo de <= 12 min por questao.
- 3 questoes medium de padrao recorrente: consolida raciocinio. Exemplo: problemas que voce ja errou antes.
- 1 questao timed com limite agressivo: treina pressao real. Exemplo: resolver medium em 20-25 min.

## Simulado da semana

- Duracao: 75 min
- Formato:
  - 1 easy
  - 2 medium
- Regra: cada erro precisa gerar uma acao concreta de prevencao

Pos-simulado:

- Reescrever a pior solucao da semana do zero.
- Comparar tempo da versao antiga vs nova.

## Criterios de aprovacao

- Melhorar pelo menos 15% no tema mais fraco
- Reduzir retrabalho de codigo
- Aumentar confianca em leitura do enunciado

Indicadores adicionais:

- Reducao de pelo menos 30% em erros repetidos.
- Pelo menos 1 melhoria de complexidade em questao refeita.

## Revisao de erros

No fim da semana, gerar ranking:

- Erros eliminados
- Erros reduzidos
- Erros ainda ativos

Fechar com 3 metas objetivas para a semana final.

## Testes e checklist de validacao

Para comprovar melhoria real, execute:

- Repeticao de 2 questoes antigas erradas (sem consulta).
- 1 questao nova do mesmo padrao.
- Comparativo de tempo e taxa de acerto.

Checklist de submissao:

- [ ] Cada erro possui acao preventiva escrita.
- [ ] Houve repeticao de problemas antigos.
- [ ] O tempo medio caiu no tema mais fraco.
- [ ] A solucao final esta mais simples que a primeira versao.

## Lista de exercicios reais por plataforma

Beecrowd:

- 1029 - Fibonacci, How Many Calls?: identificar desperdicio e otimizar.
- 1068 - Parenthesis Balance I: excelente para revisar erro de pilha.
- 1551 - Complete Sentence: contagem/frequencia de caracteres.

HackerRank (Java):

- Java 1D Array: detectar caminho valido com bordas.
- Java Regex: validacao por regra com risco de erro de detalhe.
- Java Arraylist: leitura e acesso com tratamento de falha.

LeetCode:

- 121. Best Time to Buy and Sell Stock: padrao simples de varredura.
- 53. Maximum Subarray: reforco de DP/varredura.
- 424. Longest Repeating Character Replacement: janela deslizante para quem erra borda.

## Exemplos de codigo por item

Revisao do tema:

- Top 10 erros: `erros.merge("off-by-one", 1, Integer::sum);`
- Causa raiz: `Map<String, List<String>> causas = new HashMap<>();`
- Padrao por tras do erro: `if (erro.contains("substring")) tema = "janela";`
- Contramedida: `regras.add("escrever 3 bordas antes de codar");`

Exercicios praticos:

- Tema mais fraco: `for (int i = 0; i < 8; i++) resolverTemaA();`
- Tema secundario: `for (int i = 0; i < 6; i++) resolverTemaB();`
- Manutencao: `resolverEasy(); resolverEasy(); resolverMedium(); resolverMedium();`
- Timed: `if (tempoMin >= 25) finalizarParcial();`

Testes e checklist:

- Repetir antigo: `assert resolverSemConsulta("questao-antiga") == true;`
- Questao nova mesmo padrao: `assert resolver("janela-nova") != null;`
- Comparar tempo: `melhora = tempoAnterior - tempoAtual;`

Plataformas (codigo base):

- LeetCode 121: `min = Math.min(min, p); lucro = Math.max(lucro, p - min);`
- LeetCode 53: `atual = Math.max(x, atual + x);`
- LeetCode 424: `while ((r - l + 1) - maxFreq > k) l++;`

