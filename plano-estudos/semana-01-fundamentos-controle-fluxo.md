# Semana 01 - Fundamentos e controle de fluxo

## Objetivo

Ganhar velocidade com estrutura basica de logica em Java: variaveis, condicoes, repeticoes, entrada/saida e metodos simples.

## Revisao do tema

Revise os pontos abaixo antes de codar:

- Tipos primitivos e casting: use tipo certo para evitar bugs de precisao (`int` para contagem, `double` para media). Exemplo: `double media = soma / (double) total;` evita divisao inteira.
- Operadores logicos e curto-circuito: `&&` para quando todas condicoes precisam ser verdadeiras, `||` para alternativas. Exemplo: `if (idade >= 18 && possuiDocumento) { ... }`.
- `if/else` vs `switch`: use `if/else` para regras por intervalo e `switch` para opcoes fixas. Exemplo: menu (`1`, `2`, `3`) combina melhor com `switch`.
- Lacos com parada clara: `for` quando conhece quantidade, `while` quando depende de condicao. Exemplo: `while (opcao != 0) { ... }` com atualizacao da opcao no fim do loop.
- Metodos pequenos: isole regras para testar separado. Exemplo: `boolean senhaValida(String s)` e `double calcularDesconto(double valor)`.

Padrao para qualquer questao:

1. Ler e reescrever o enunciado em 2 linhas.
2. Definir entrada, saida e regra de negocio.
3. Listar 3 casos de teste antes de implementar.

## Checklist diario (5 dias)

- [ ] Dia 1: if/else, operadores, problemas de decisao (4-6 questoes)
- [ ] Dia 2: switch e validacoes encadeadas (4-6 questoes)
- [ ] Dia 3: for/while/do-while com contadores e acumuladores (5 questoes)
- [ ] Dia 4: metodos, parametros e retorno (4-5 questoes)
- [ ] Dia 5: revisao + mini simulado (2 questoes em 45 min)

## Exercicios praticos tipo selecao

Bloco A (aquecimento):

- Classificacao por faixa: treina `if/else` por intervalo. Exemplo: entrada `nota=8.1` -> saida `APROVADO`.
- Calculo de media com validacao: treina leitura e regra de negocio. Exemplo: notas `7, 8, 9` -> media `8.0`.
- Maior/menor em N numeros: treina acumulador e comparacao. Exemplo: `5 2 9 1` -> `maior=9, menor=1`.

Bloco B (processo seletivo):

- Soma de pares e impares em [A, B]: treina loop com condicao. Exemplo: `A=1, B=5` -> `pares=6, impares=9`.
- Menu com `switch`: treina fluxo de comando interativo. Exemplo: opcoes `1,2,0` -> executa duas acoes e encerra.
- Contagem de ocorrencias: treina busca linear simples. Exemplo: lista `1 2 2 3`, alvo `2` -> `2 ocorrencias`.

Bloco C (timed):

- Problema 1 (15 min): validar senha por regras minimas. Exemplo: `Abc12345` -> valida; `abc` -> invalida.
- Problema 2 (20 min): simulador de desconto por faixa. Exemplo: `valor=180` -> `desconto 10%`, total `162`.

## Simulado da semana

- Duracao: 60 min
- Formato:
  - 2 questoes easy
  - 1 questao easy/medium
- Regra: sem consulta durante o tempo

Roteiro do simulado:

- 5 min: leitura e plano.
- 45 min: implementacao.
- 10 min: testes manuais e ajuste final.

## Criterios de aprovacao

- Acerto minimo: 70%
- Tempo medio em easy: ate 15 min
- Compila sem erros na primeira tentativa em pelo menos 60% das questoes

Indicador extra:

- Em pelo menos 2 questoes, explicar verbalmente por que escolheu `if` ou `switch`.

## Revisao de erros

No fim de cada dia, registre:

- Erro principal do dia
- Motivo do erro
- Como evitar na proxima questao
- 1 problema para repetir em 48h

## Testes e checklist de validacao

Para cada exercicio, execute no minimo:

- Caso normal (entrada esperada).
- Caso de borda (zero, negativo, vazio, limite).
- Caso invalido (quando o enunciado permitir validacao).

Checklist de submissao:

- [ ] O metodo principal esta curto e legivel.
- [ ] Nomes de variaveis explicam a regra.
- [ ] Nao existe loop sem condicao de parada clara.
- [ ] A saida esta exatamente no formato pedido.

## Lista de exercicios reais por plataforma

Beecrowd:

- 1001 - Extremely Basic: soma de dois inteiros. Exemplo: `10 9` -> `X = 19`.
- 1010 - Simple Calculate: total de compra com duas linhas de itens. Exemplo: calcula `VALOR A PAGAR`.
- 1047 - Game Time with Minutes: regra de tempo com virada de dia. Exemplo: `7 8 9 10` -> duracao correta.

HackerRank (Java):

- Java If-Else: classificacao por faixa de numero. Exemplo: `n=3` -> `Weird`.
- Java Loops I: tabuada com `for`. Exemplo: `n=2` -> imprime `2 x i = ...`.
- Java End-of-file: leitura ate EOF. Exemplo: imprime linha numerada ate acabar entrada.

LeetCode:

- 412. Fizz Buzz: condicoes em sequencia. Exemplo: `n=5` -> `1,2,Fizz,4,Buzz`.
- 9. Palindrome Number: decisao e reversao de numero. Exemplo: `121` -> `true`.
- 13. Roman to Integer: parsing simples de string. Exemplo: `MCMXCIV` -> `1994`.

## Exemplos de codigo por item

Revisao do tema:

- Tipos e casting: `double media = soma / (double) total;`
- Curto-circuito: `if (idade >= 18 && possuiDocumento) aprovado = true;`
- `if/else` vs `switch`: `switch (op) { case 1 -> sacar(); default -> erro(); }`
- Laco com parada: `while (opcao != 0) opcao = scanner.nextInt();`
- Metodo pequeno: `boolean senhaValida(String s) { return s.length() >= 8; }`

Exercicios praticos:

- Classificacao: `status = nota >= 7 ? "APROVADO" : "REPROVADO";`
- Media com validacao: `if (nota < 0 || nota > 10) throw new IllegalArgumentException();`
- Maior/menor: `maior = Math.max(maior, x); menor = Math.min(menor, x);`
- Soma pares/impares: `if (i % 2 == 0) pares += i; else impares += i;`
- Contagem de ocorrencias: `if (nums[i] == alvo) cont++;`

Testes e checklist:

- Caso feliz: `assert calcularMedia(7, 8, 9) == 8.0;`
- Caso de borda: `assert contarOcorrencias(new int[]{}, 2) == 0;`
- Caso invalido: `assertThrows(IllegalArgumentException.class, () -> validarNota(12));`

Plataformas (codigo base):

- Fizz Buzz: `if (i % 15 == 0) out.add("FizzBuzz");`
- Palindrome Number: `while (x > rev) { rev = rev * 10 + x % 10; x /= 10; }`
- Roman to Integer: `total += map.get(s.charAt(i));`

