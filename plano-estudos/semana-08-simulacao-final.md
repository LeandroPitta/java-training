# Semana 08 - Simulacao final de processo seletivo

## Objetivo

Executar ciclo completo de prova tecnica com padrao real: tempo limitado, priorizacao, comunicacao de solucao e pos-analise.

## Revisao do tema

Checklist mental para prova final:

- Ler enunciado ativamente: escreva entrada, saida e limites em uma linha. Exemplo: `n` ate `10^5` ja elimina solucoes `O(n^2)`.
- Abordagem segura primeiro: priorize a que voce implementa com menos erro. Exemplo: comecar por hash `O(n)` em vez de tentativa complexa.
- Estimar complexidade antes: evita terminar com solucao inviavel. Exemplo: 3 loops aninhados em entrada grande tende a falhar no tempo.
- Codigo claro: metodos curtos facilitam debug em prova. Exemplo: `parseEntrada()`, `resolver()`, `imprimirSaida()`.
- Tempo final de teste: sempre reservar bloco para validar bordas. Exemplo: ultimos 15-20 min para testes e formato de saida.

Script de explicacao da solucao (treino oral/escrito):

1. "Vou usar X porque reduz comparacoes e simplifica casos de borda".
2. "A complexidade de tempo e ... e memoria ...".
3. "Testei com caso normal, borda e limite".

## Checklist diario (5 dias)

- [ ] Dia 1: simulado completo #1 (90 min)
- [ ] Dia 2: revisao detalhada do simulado #1 + refatoracao
- [ ] Dia 3: simulado completo #2 (90 min)
- [ ] Dia 4: revisao detalhada do simulado #2 + repeticao de erros
- [ ] Dia 5: simulado completo #3 (90 min) + fechamento do ciclo

## Exercicios praticos tipo selecao

- Pacote misto com 3 questoes por simulado:
  - 1 easy: aquecimento e garantia de pontos. Exemplo: validacao de palindromo/duplicados.
  - 1 medium: foco em algoritmo principal. Exemplo: hash + prefixo para soma alvo.
  - 1 medium com borda ou otimizacao: foco em robustez. Exemplo: janela deslizante com entrada limite.

Temas sugeridos para os 3 simulados:

- Simulado 1: arrays/strings + hash. Exemplo: `Two Sum` + anagramas.
- Simulado 2: busca/ordenacao + intervalo. Exemplo: merge de intervalos + busca binaria.
- Simulado 3: mix geral com enunciado longo. Exemplo: simulacao de operacoes com varias regras.

## Simulado da semana

- Total: 3 simulados completos
- Regra:
  - sem consulta durante prova
  - 20 min de debrief apos cada prova

Debrief obrigatorio por simulado:

- Questao que mais rendeu pontos rapidamente.
- Questao em que faltou estrategia.
- Ajuste de processo para o proximo simulado.

## Criterios de aprovacao

- Acerto medio >= 70%
- Entrega de ao menos 2/3 questoes por simulado
- Justificativa de complexidade coerente em todas as solucoes
- Queda clara de erros repetidos

## Revisao de erros

Fechamento final:

- Top 5 erros antigos que foram corrigidos
- Top 3 erros que ainda exigem manutencao
- Plano de continuidade para proximas 4 semanas

## Testes e checklist de validacao

Protocolo de teste por simulado:

- 3 testes por questao (normal, borda, limite).
- 1 reexecucao imediata da pior questao sem consulta.
- 1 revisao de formato de saida em todas as questoes.

Checklist de submissao:

- [ ] Todas as questoes possuem pelo menos 3 testes manuais.
- [ ] A complexidade foi declarada em cada resposta.
- [ ] O tempo total ficou dentro do limite.
- [ ] Houve melhoria entre simulado 1, 2 e 3.

## Lista de exercicios reais por plataforma

Beecrowd:

- 1025 - Where is the Marble?: busca e ordenacao sob formato de entrada real.
- 1244 - Sort by Length: ordenacao com criterio especifico.
- 1259 - Even and Odd: regra de ordenacao combinada e validacao de saida.

HackerRank (Java):

- Java Comparator: ordenacao de objetos com multiplas regras.
- Queue using Two Stacks: simulacao de estrutura com operacoes.
- New Year Chaos: contagem de trocas e regra de limite.

LeetCode:

- 56. Merge Intervals: classico de entrevista.
- 215. Kth Largest Element in an Array: heap/quickselect.
- 981. Time Based Key-Value Store: estrutura + busca binaria em historico.

## Exemplos de codigo por item

Revisao do tema:

- Extrair restricoes: `if (n > 100000) usarSolucaoLinear();`
- Abordagem segura: `if (conhecoHash) return resolverComHash(nums);`
- Complexidade antes: `String custo = "O(n log n)";`
- Codigo claro: `resultado = resolver(entrada); imprimir(resultado);`
- Tempo final para testes: `if (tempoRestante >= 15) rodarTestes();`

Exercicios praticos:

- Easy: `boolean dup = containsDuplicate(nums);`
- Medium: `int[] ans = twoSum(nums, alvo);`
- Medium com borda: `if (nums.length == 0) return 0;`
- Simulado 1/2/3: `for (int s = 1; s <= 3; s++) executarSimulado(s);`

Testes e checklist:

- Normal: `assert resolver(casoNormal).equals(esperado);`
- Borda: `assert resolver(casoBorda) != null;`
- Limite: `assert resolver(casoGrande).size() > 0;`
- Reexecucao: `resultado2 = resolver(piorQuestao);`

Plataformas (codigo base):

- LeetCode 56: `if (cur[0] <= last[1]) last[1] = Math.max(last[1], cur[1]);`
- LeetCode 215: `pq.offer(x); if (pq.size() > k) pq.poll();`
- LeetCode 981: `int idx = upperBound(lista, timestamp);`

## Proximo ciclo (manutencao)

- 3 dias por semana
- 2 questoes por dia
- 1 simulado quinzenal
- 1 revisao mensal de metricas

