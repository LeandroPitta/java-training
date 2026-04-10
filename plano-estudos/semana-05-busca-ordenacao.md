# Semana 05 - Busca e Ordenacao

## Objetivo

Aplicar busca e ordenacao para resolver problemas de forma previsivel e eficiente.

## Revisao do tema

Conceitos de revisao:

- Busca binaria exige dados ordenados. Exemplo: `while (l <= r) { int m = (l + r) / 2; ... }` encontra alvo em `O(log n)`.
- Comparadores definem regra de ordenacao. Exemplo: `lista.sort(Comparator.comparing(Pessoa::getIdade));`.
- Top-k: nem sempre precisa ordenar tudo. Exemplo: heap de tamanho `k` pode ser melhor que `sort` completo.
- Intervalos: ordene pelo inicio e una quando houver sobreposicao. Exemplo: se `atual.inicio <= ultimo.fim`, faca merge.
- Custo: prefira algoritmo com menor complexidade para o tamanho esperado da entrada.

Decisao rapida:

- Precisa localizar em ordenado -> busca binaria.
- Precisa unificar periodos/faixas -> ordenar + varrer.
- Precisa apenas dos maiores K -> heap pode ser melhor que ordenar tudo.

## Checklist diario (5 dias)

- [ ] Dia 1: busca binaria em arrays ordenados (4 questoes)
- [ ] Dia 2: ordenacao com comparadores (3-4 questoes)
- [ ] Dia 3: intervalos (merge, sobreposicao) (3-4 questoes)
- [ ] Dia 4: top-k e ranking basico (3 questoes)
- [ ] Dia 5: revisao + mini simulado (3 questoes em 70 min)

## Exercicios praticos tipo selecao

Bloco A (aquecimento):

- Primeira e ultima ocorrencia: treina busca binaria adaptada. Exemplo: `[1,2,2,2,3]`, alvo `2` -> `[1,3]`.
- Inserir em posicao ordenada: treina busca de indice de insercao. Exemplo: `[1,3,5]`, valor `4` -> indice `2`.
- Reordenar por multiplos criterios: treina `Comparator` composto. Exemplo: ordenar por nota desc e nome asc.

Bloco B (processo seletivo):

- Mesclar intervalos: treina ordenacao + varredura. Exemplo: `[[1,3],[2,6],[8,10]]` -> `[[1,6],[8,10]]`.
- K maiores elementos: treina heap minimo de tamanho `k`. Exemplo: `[3,2,1,5,6,4]`, `k=2` -> `[6,5]`.
- Agendar reunioes sem conflito: treina validacao de sobreposicao. Exemplo: `[[9,10],[10,11]]` -> sem conflito.

Bloco C (timed):

- Problema 1 (20 min): pico em array de montanha. Exemplo: `[0,2,4,3,1]` -> indice do pico `2`.
- Problema 2 (25 min): capacidade minima em D dias. Exemplo: pesos `[1,2,3,1,1]`, `D=4` -> capacidade `3`.

## Simulado da semana

- Duracao: 90 min
- Formato:
  - 1 easy
  - 2 medium
- Regra: comparar 2 abordagens quando possivel

Roteiro do simulado:

- 10 min: definir abordagem A e B.
- 65 min: implementar a melhor abordagem.
- 15 min: revisar e validar casos extremos.

## Criterios de aprovacao

- Acerto minimo: 70%
- Escolha correta de algoritmo em pelo menos 80% das questoes
- Tempo medio em medium: ate 30 min

## Revisao de erros

Para cada problema nao resolvido:

- Onde travou
- Qual pista destravou
- Qual padrao era esperado
- Qual problema parecido vai repetir amanha

## Testes e checklist de validacao

Casos de teste obrigatorios:

- Array ordenado com elementos repetidos.
- Array nao ordenado quando o algoritmo exige ordenacao previa.
- Intervalos totalmente sobrepostos e totalmente separados.
- Entrada grande para observar tempo de execucao.

Checklist de submissao:

- [ ] Pre-condicoes do algoritmo estao garantidas.
- [ ] Comparador nao possui ambiguidade.
- [ ] Resultado final esta ordenado quando esperado.
- [ ] Complexidade esta alinhada com a estrategia escolhida.

## Lista de exercicios reais por plataforma

Beecrowd:

- 1025 - Where is the Marble?: ordenar e localizar ocorrencia.
- 1162 - Train Swapping: contagem de trocas em ordenacao simples.
- 1244 - Sort by Length: ordenacao de palavras por tamanho.

HackerRank (Java):

- Java Sorting: ordenar lista de objetos com regras.
- Intro to Tutorial Challenges: busca de valor em array.
- Closest Numbers: ordenar e achar menor diferenca.

LeetCode:

- 34. Find First and Last Position of Element in Sorted Array.
- 56. Merge Intervals.
- 215. Kth Largest Element in an Array.

## Exemplos de codigo por item

Revisao do tema:

- Busca binaria: `while (l <= r) { int m = l + (r - l) / 2; }`
- Comparator: `lista.sort(Comparator.comparing(Pessoa::getNome));`
- Top-k com heap: `PriorityQueue<Integer> pq = new PriorityQueue<>();`
- Merge de intervalos: `if (ini <= fimAtual) fimAtual = Math.max(fimAtual, fim);`
- Custo: `// O(n log n) por causa do sort`

Exercicios praticos:

- Primeira/ultima ocorrencia: `ans = m; r = m - 1;`
- Insercao ordenada: `return l; // indice de insercao`
- Ordenacao multipla: `cmp = byNota.reversed().thenComparing(byNome);`
- K maiores: `pq.offer(x); if (pq.size() > k) pq.poll();`
- Reunioes: `if (atual[0] < prev[1]) return false;`

Testes e checklist:

- Repetidos: `assert range(new int[]{1,2,2,2,3},2)[0] == 1;`
- Nao ordenado: `Arrays.sort(nums);`
- Intervalos disjuntos: `assert merge(new int[][]{{1,2},{3,4}}).length == 2;`

Plataformas (codigo base):

- LeetCode 34: `int left = lowerBound(nums, target);`
- LeetCode 56: `Arrays.sort(intervals, Comparator.comparingInt(a -> a[0]));`
- LeetCode 215: `return quickSelect(nums, 0, n - 1, n - k);`

