# Semana 06 - Simulados progressivos

## Objetivo

Treinar desempenho sob pressao de tempo, com foco em consistencia e comunicacao da solucao.

## Revisao do tema

Foco da semana:

- Gestao de tempo: divida por etapa para nao estourar prazo. Exemplo: 20 min codar + 5 min testar por questao easy.
- Priorizacao: resolva primeiro o que tem maior chance de acerto. Exemplo: fechar uma easy completa antes de iniciar medium longa.
- Leitura ativa: sublinhe entrada, saida e restricoes. Exemplo: se enunciado pede ordem original, nao ordene o array.
- Fallback ao travar: troque de questao temporariamente. Exemplo: travou 15 min, anote tentativa e avance para proxima.
- Comunicacao objetiva: explique "ideia -> estrutura -> complexidade" em 3 frases para treinar entrevista tecnica.

Regra de prova:

- Se ficar 12-15 min travado, registrar tentativa e seguir para a proxima.

## Checklist diario (5 dias)

- [ ] Dia 1: simulado curto (60 min, 2 questoes) + revisao
- [ ] Dia 2: treino de speed-run (3 easy em 45 min)
- [ ] Dia 3: simulado medio (75 min, 3 questoes)
- [ ] Dia 4: retrabalho das 2 piores questoes da semana
- [ ] Dia 5: simulado completo (90 min, 3 questoes)

## Exercicios praticos tipo selecao

- Mix de arrays, strings, hash e busca: treina troca rapida de padrao. Exemplo: questao 1 com string, questao 2 com hash.
- Problema com otimizacao: treina migrar de `O(n^2)` para `O(n)`/`O(n log n)`. Exemplo: `Two Sum` sem dupla iteracao.
- Problema com borda: treina robustez. Exemplo: entrada vazia, `n=1`, valores negativos.
- Problema com enunciado longo: treina leitura ativa e extracao de regras. Exemplo: simular sistema com varias operacoes.

Pacotes recomendados por dia:

- Pacote 1: 2 easy + 1 medium (60 min). Exemplo: foco em acertar 100% das easy.
- Pacote 2: 1 easy + 2 medium (75 min). Exemplo: priorizar medium de hash/array.
- Pacote 3: 3 medium curtas (90 min). Exemplo: treinar resistencia e controle de tempo.

## Simulado da semana

- Duracao total da semana em simulados: 3h45
- Regra:
  - sem consulta durante prova
  - 15 min pos-prova para analise de estrategia

Debrief pos-simulado (obrigatorio):

- Qual foi a primeira questao escolhida e por que.
- Onde perdeu mais tempo.
- Qual erro poderia ser evitado com um teste simples.

## Criterios de aprovacao

- Acerto minimo: 65% nos simulados
- Entrega completa de pelo menos 2 simulados
- Queda de erros por distracao em relacao a semana 5

## Revisao de erros

Template rapido:

- Erro:
- Impacto no resultado:
- Sinal de alerta que foi ignorado:
- Nova regra pessoal:

## Testes e checklist de validacao

Protocolo minimo por questao do simulado:

- 1 teste feliz.
- 1 teste de borda.
- 1 teste de estresse pequeno (entrada maior).

Checklist de submissao:

- [ ] A questao escolhida primeiro era a mais segura.
- [ ] Houve tempo reservado para testar (>= 10 min finais).
- [ ] Os erros do simulado anterior nao se repetiram.
- [ ] Complexidade foi registrada para cada solucao.

## Lista de exercicios reais por plataforma

Beecrowd:

- 1069 - Diamonds and Sand: stack + parsing rapido.
- 1104 - Exchanging Cards: set e comparacao de colecoes.
- 1259 - Even and Odd: ordenacao com regra mista.

HackerRank (Java):

- Java Priority Queue: simulacao com ordenacao por prioridade.
- Balanced Brackets: validacao com stack sob tempo.
- Sherlock and Array: soma prefixo/sufixo com bordas.

LeetCode:

- 217. Contains Duplicate: warm-up rapido com set.
- 238. Product of Array Except Self: medium curta com prefixo/sufixo.
- 560. Subarray Sum Equals K: medium de hash muito cobrada.

## Exemplos de codigo por item

Revisao do tema:

- Gestao de tempo: `long inicio = System.currentTimeMillis();`
- Priorizacao: `questoes.sort(Comparator.comparingInt(Questao::getDificuldade));`
- Leitura ativa: `String regra = "manter ordem original";`
- Fallback: `if (minTravado >= 15) indiceQuestao++;`
- Comunicacao: `System.out.println("O(n) tempo, O(n) memoria");`

Exercicios praticos:

- Mix de padroes: `Map<Integer, Integer> visto = new HashMap<>();`
- Otimizacao: `if (visto.containsKey(k - nums[i])) return true;`
- Borda: `if (nums == null || nums.length == 0) return 0;`
- Enunciado longo: `switch (op) { case "ADD" -> add(); default -> erro(); }`

Testes e checklist:

- Teste feliz: `assert resolver(new int[]{1,2,3}) == esperado;`
- Teste borda: `assert resolver(new int[]{}) == 0;`
- Estresse pequeno: `int[] grande = new int[10000];`

Plataformas (codigo base):

- LeetCode 217: `if (!set.add(n)) return true;`
- LeetCode 238: `ans[i] = prefixo[i] * sufixo[i];`
- LeetCode 560: `count += freq.getOrDefault(soma - k, 0);`

