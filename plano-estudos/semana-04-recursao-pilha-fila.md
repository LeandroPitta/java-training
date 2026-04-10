# Semana 04 - Recursao, Pilha e Fila

## Objetivo

Fortalecer pensamento sequencial e de estado com recursao e estruturas lineares classicas.

## Revisao do tema

Topicos essenciais:

- Recursao: precisa de caso base e chamada para problema menor. Exemplo: `fat(n) = n * fat(n - 1)` com base `fat(0) = 1`.
- Pilha (LIFO): ultimo que entra e o primeiro que sai. Exemplo: parenteses balanceados com `push` em `'('` e `pop` em `')'`.
- Fila (FIFO): primeiro que entra e o primeiro que sai. Exemplo: BFS em grade usando `Queue<int[]>`.
- Iterativo vs recursivo: iterativo usa loop explicito; recursivo usa pilha de chamadas. Exemplo: soma de array pode ser feita dos dois jeitos.
- Stack overflow: evite recursao muito profunda sem controle. Exemplo: para grande volume, prefira versao iterativa quando possivel.

Regra pratica:

- Se a solucao visita niveis por distancia minima -> fila/BFS.
- Se a solucao depende do ultimo aberto -> pilha.
- Se o problema se divide em subproblemas iguais -> recursao.

## Checklist diario (5 dias)

- [ ] Dia 1: recursao basica (fatorial, fibonacci com memo, soma) (4 questoes)
- [ ] Dia 2: recursao em strings/arrays (3-4 questoes)
- [ ] Dia 3: problemas de pilha (parenteses, RPN) (4 questoes)
- [ ] Dia 4: fila e BFS simples (3 questoes)
- [ ] Dia 5: revisao + mini simulado (2-3 questoes em 60 min)

## Exercicios praticos tipo selecao

Bloco A (aquecimento):

- Parenteses balanceados: treina `Stack` para abertura/fechamento. Exemplo: `"([])"` -> valido.
- Expressao pos-fixa: treina pilha com operadores. Exemplo: `"2 3 + 4 *"` -> `20`.
- Fila de atendimento: treina `Queue` e ordem FIFO. Exemplo: `A,B,C` -> saida `A` primeiro.

Bloco B (processo seletivo):

- Menor numero de passos em grade (BFS): treina camadas por distancia. Exemplo: grade 3x3 sem bloqueio -> menor caminho `4`.
- Gerar combinacoes (backtracking): treina escolha/desfazer. Exemplo: `n=4, k=2` -> `[1,2], [1,3], ...`.
- Inverter pilha com recursao: treina uso de chamada recursiva como apoio. Exemplo: topo `3,2,1` -> `1,2,3`.

Bloco C (timed):

- Problema 1 (20 min): historico de navegador com pilha. Exemplo: `visit A, visit B, back` -> pagina `A`.
- Problema 2 (25 min): menor caminho em matriz binaria. Exemplo: matriz com obstaculos -> retornar distancia minima.

## Simulado da semana

- Duracao: 90 min
- Formato:
  - 1 easy
  - 1 medium
  - 1 medium (estrutura)
- Regra: focar em casos de parada e casos de borda

Roteiro do simulado:

- 15 min: desenhar caso base e fluxo.
- 60 min: implementar.
- 15 min: validar limites e entradas vazias.

## Criterios de aprovacao

- Acerto minimo: 65%
- Nenhum loop infinito/recursao sem parada
- Casos de borda cobertos em 100% das questoes

## Revisao de erros

Checklist de validacao antes de submeter:

- Caso base esta correto?
- Estrutura escolhida simplifica ou complica?
- Existe off-by-one?
- Testei entrada vazia/nula?

## Testes e checklist de validacao

Casos de teste obrigatorios:

- Estrutura vazia.
- Estrutura com 1 elemento.
- Estrutura com profundidade maior.
- Entrada invalida (quando aplicavel).

Checklist de submissao:

- [ ] Recursao sempre converge para caso base.
- [ ] Pilha/fila nao gera `NullPointerException`.
- [ ] A ordem de processamento esta correta.
- [ ] O algoritmo passou em pelo menos 4 testes manuais.

## Lista de exercicios reais por plataforma

Beecrowd:

- 1068 - Parenthesis Balance I: validacao de parenteses com pilha.
- 1110 - Throwing Cards Away: simulacao de fila.
- 1111 - Desrugenstein: busca em grade com BFS.

HackerRank (Java):

- Java Stack: parenteses balanceados.
- Java Dequeue: janela com distintos usando deque/mapa.
- BFS: Shortest Reach in a Graph: BFS por nivel em grafo.

LeetCode:

- 20. Valid Parentheses: stack classica.
- 150. Evaluate Reverse Polish Notation: pilha de operandos.
- 542. 01 Matrix: BFS de multiplas fontes.

## Exemplos de codigo por item

Revisao do tema:

- Recursao: `int fat(int n) { return n == 0 ? 1 : n * fat(n - 1); }`
- Pilha: `if (c == '(') st.push(c); else st.pop();`
- Fila/BFS: `Queue<int[]> q = new ArrayDeque<>();`
- Iterativo: `for (int x : nums) soma += x;`
- Controle de profundidade: `if (n > 10000) return;`

Exercicios praticos:

- Parenteses: `if (map.get(c) != st.pop()) return false;`
- RPN: `st.push(a + b);`
- Fila de atendimento: `String atual = fila.poll();`
- BFS em grade: `q.offer(new int[]{r, c, dist + 1});`
- Combinacoes: `backtrack(i + 1, atual); atual.remove(atual.size() - 1);`

Testes e checklist:

- Estrutura vazia: `assert isValid("");`
- Um elemento: `assert evalRPN(new String[]{"2"}) == 2;`
- Profundidade maior: `assert minSteps(gridGrande) > 0;`

Plataformas (codigo base):

- LeetCode 20: `if (st.isEmpty()) return false;`
- LeetCode 150: `int b = st.pop(), a = st.pop();`
- LeetCode 542: `dist[nr][nc] = dist[r][c] + 1;`

