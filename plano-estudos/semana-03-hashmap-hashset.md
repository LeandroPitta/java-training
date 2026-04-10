# Semana 03 - HashMap e HashSet

## Objetivo

Usar estruturas de hash para trocar solucoes O(n^2) por O(n), melhorando performance e clareza.

## Revisao do tema

Pontos de revisao:

- `HashMap` para associacao chave-valor e `HashSet` para evitar repeticao. Exemplo: contar frequencia usa map; detectar duplicado usa set.
- Operacoes medias `O(1)`: `put`, `get`, `containsKey` costumam ser constantes. Exemplo: trocar busca linear por `map.get(x)`.
- Frequencia com `getOrDefault`: simplifica incremento. Exemplo: `freq.put(x, freq.getOrDefault(x, 0) + 1);`.
- Verificacao de existencia: confirme antes de usar valor. Exemplo: `if (map.containsKey(alvo)) { ... }`.
- Lookup direto no lugar de dupla comparacao: em `Two Sum`, guarde valor ja visto e consulte complemento em tempo constante.

Perguntas rapidas antes de codar:

- "Eu estou comparando todos contra todos?"
- "Posso armazenar o que ja vi para decidir em O(1)?"

## Checklist diario (5 dias)

- [ ] Dia 1: contagem de frequencia com HashMap (4 questoes)
- [ ] Dia 2: deduplicacao e intersecao com HashSet (4 questoes)
- [ ] Dia 3: lookup rapido (two sum e variacoes) (4 questoes)
- [ ] Dia 4: agrupamento por chave e ranking simples (3-4 questoes)
- [ ] Dia 5: revisao + mini simulado (3 questoes em 60 min)

## Exercicios praticos tipo selecao

Bloco A (aquecimento):

- Two Sum: treina lookup em `HashMap`. Exemplo: `[2,7,11,15]`, alvo `9` -> indices `0,1`.
- Intersecao sem duplicar: treina `HashSet` para unicidade. Exemplo: `[1,2,2]` e `[2,2,3]` -> `[2]`.
- Contar palavras unicas: treina normalizacao e frequencia. Exemplo: `"oi oi java"` -> `2 unicas`.

Bloco B (processo seletivo):

- Top K frequentes: treina contagem + ordenacao/heap. Exemplo: `[1,1,1,2,2,3]`, `k=2` -> `[1,2]`.
- Agrupar anagramas: treina chave por assinatura. Exemplo: `[eat, tea, tan, ate]` -> grupos `[[eat,tea,ate],[tan]]`.
- Repeticao em janela K: treina estado recente com hash. Exemplo: `[1,2,3,1]`, `k=3` -> `true`.

Bloco C (timed):

- Problema 1 (20 min): first missing positive (simplificada). Exemplo: `[1,2,0]` -> `3`.
- Problema 2 (25 min): detectar ciclo de repeticao em stream curta. Exemplo: `A B C A` -> ciclo em `A`.

## Simulado da semana

- Duracao: 90 min
- Formato:
  - 1 easy
  - 2 medium
- Regra: justificar estrutura escolhida antes de codar

Roteiro do simulado:

- Questao 1: resolver com hash em ate 15 min.
- Questao 2: comparar opcao ordenacao x hash.
- Questao 3: tratar caso de borda explicitamente.

## Criterios de aprovacao

- Acerto minimo: 70%
- Tempo medio em easy: ate 12 min
- Pelo menos 2 solucoes otimizadas de O(n^2) para O(n)

## Revisao de erros

Para cada erro, registrar:

- Solucao inicial
- Solucao corrigida
- Diferenca de complexidade
- Regra pratica para nao repetir o erro

## Testes e checklist de validacao

Casos de teste obrigatorios:

- Dados com todos elementos iguais.
- Dados sem solucao valida.
- Dados com negativos/zeros.
- Dados grandes para validar performance.

Checklist de submissao:

- [ ] Estrutura de hash foi inicializada corretamente.
- [ ] Nao ha sobrescrita indevida de chave.
- [ ] Complexidade final realmente melhorou.
- [ ] Resultado nao possui duplicatas inesperadas.

## Lista de exercicios reais por plataforma

Beecrowd:

- 1025 - Where is the Marble?: busca de ocorrencia com ordenacao. Exemplo: reportar primeira posicao do valor.
- 1256 - Hash Tables: simulacao de tabela hash com encadeamento.
- 1260 - Hardwood Species: contagem de frequencia por nome.

HackerRank (Java):

- Java Hashset: contar pares distintos.
- Java Map: agenda telefonica com busca por chave.
- Java Sort: ordenar objetos com comparador.

LeetCode:

- 1. Two Sum: lookup em mapa.
- 49. Group Anagrams: agrupamento por assinatura.
- 347. Top K Frequent Elements: frequencia + heap/bucket.

## Exemplos de codigo por item

Revisao do tema:

- Frequencia: `freq.put(x, freq.getOrDefault(x, 0) + 1);`
- Duplicado com set: `if (!vistos.add(x)) return true;`
- Busca por chave: `if (map.containsKey(alvo)) return map.get(alvo);`
- Intersecao: `if (setA.contains(x)) intersecao.add(x);`
- Otimizacao: `if (visto.containsKey(k - nums[i])) return ...;`

Exercicios praticos:

- Two Sum: `visto.put(nums[i], i);`
- Top K: `pq.offer(entry); if (pq.size() > k) pq.poll();`
- Anagramas: `char[] c = palavra.toCharArray(); Arrays.sort(c);`
- Janela K: `if (i - map.get(x) <= k) return true;`
- Palavras unicas: `texto.toLowerCase().split("\\s+")`

Testes e checklist:

- Sem solucao: `assert twoSum(new int[]{1,2,3}, 7) == null;`
- Todos iguais: `assert topK(new int[]{2,2,2}, 1).get(0) == 2;`
- Negativos: `assert containsDuplicate(new int[]{-1,-2,-1});`

Plataformas (codigo base):

- LeetCode 1: `if (map.containsKey(target - n)) return new int[]{map.get(target - n), i};`
- LeetCode 49: `grupos.computeIfAbsent(chave, k -> new ArrayList<>()).add(s);`
- LeetCode 347: `freq.forEach((n, f) -> buckets[f].add(n));`

