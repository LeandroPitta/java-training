# Semana 02 - Arrays e Strings

## Objetivo

Dominar manipulacao de arrays e strings, com foco em padroes comuns de entrevista: contagem, busca, duas pontas e janela simples.

## Revisao do tema

Conceitos-chave da semana:

- Percurso linear com acumulador: varra uma vez e atualize resposta parcial. Exemplo: `for (int n : nums) soma += n;`.
- `char[]` vs `String`: `char[]` facilita trocar caracteres, `String` e imutavel. Exemplo: para editar, use `StringBuilder`.
- Comparacao de strings: use `equals`, nao `==`. Exemplo seguro: `"ok".equals(status)` evita `NullPointerException`.
- Duas pontas: use indices `i` e `j` para comparar extremos sem loops aninhados. Exemplo: validacao de palindromo em `O(n)`.
- Janela deslizante: mantenha intervalo `[left, right]` e ajuste conforme regra. Exemplo: maior soma de subarray de tamanho `k`.

Heuristica de escolha rapida:

- Se precisa contar frequencia -> pensar em array de contagem ou `HashMap`.
- Se precisa extremos/inversao -> pensar em duas pontas.
- Se precisa subarray/substring continua -> pensar em janela.

## Checklist diario (5 dias)

- [ ] Dia 1: percorrer arrays e estatisticas basicas (4-5 questoes)
- [ ] Dia 2: strings (palindromo, vogais, frequencia) (4-5 questoes)
- [ ] Dia 3: duas pontas em string/array ordenado (3-4 questoes)
- [ ] Dia 4: janela deslizante simples (3-4 questoes)
- [ ] Dia 5: revisao + mini simulado (2 questoes em 50 min)

## Exercicios praticos tipo selecao

Bloco A (aquecimento):

- Remover duplicados de array ordenado: treina ponteiro lento/rapido. Exemplo: `[1,1,2,2,3]` -> `[1,2,3]`.
- Verificar palindromo ignorando espacos: treina duas pontas. Exemplo: `"a saca"` -> `true`.
- Primeiro caractere nao repetido: treina contagem de frequencia. Exemplo: `"swiss"` -> `w`.

Bloco B (processo seletivo):

- Verificar anagrama: treina comparacao por frequencia. Exemplo: `"roma"` e `"amor"` -> `true`.
- Maior subarray com soma alvo: treina janela/acumulador. Exemplo: `[1,2,1,1,1]`, alvo `3` -> tamanho `3`.
- Buscar par com soma K: treina hash ou duas pontas. Exemplo: `[2,7,11,15]`, `k=9` -> indices `0,1`.

Bloco C (timed):

- Problema 1 (20 min): comprimir string (run length). Exemplo: `"aaabb"` -> `"a3b2"`.
- Problema 2 (25 min): maior substring sem repeticao. Exemplo: `"abcabcbb"` -> `3`.

## Simulado da semana

- Duracao: 75 min
- Formato:
  - 1 easy
  - 2 medium
- Regra: escrever complexidade antes da implementacao

Roteiro do simulado:

- 10 min: mapear padrao da questao.
- 50 min: codar 2 questoes.
- 15 min: resolver 1 questao restante e testar.

## Criterios de aprovacao

- Acerto minimo: 65%
- Explicar complexidade corretamente em 80% das questoes
- Reduzir erros de caso de borda em relacao a semana 1

## Revisao de erros

Classifique cada erro em:

- sintaxe
- logica
- borda
- complexidade
- tempo

Repita no domingo 2 problemas com mais erro da semana.

## Testes e checklist de validacao

Casos de teste obrigatorios:

- Entrada vazia (`""`, array tamanho 0).
- Entrada unitario (1 elemento/caractere).
- Entrada com repeticoes massivas.
- Entrada com caracteres especiais e espacos (quando aplicavel).

Checklist de submissao:

- [ ] Complexidade foi anotada antes de enviar.
- [ ] Nao ha acesso fora do limite do array.
- [ ] O algoritmo funciona para `n=0` e `n=1`.
- [ ] Existem pelo menos 3 testes manuais registrados.

## Lista de exercicios reais por plataforma

Beecrowd:

- 1172 - Array Replacement I: manipulacao basica de array. Exemplo: trocar valores <= 0 por `1`.
- 1179 - Array Fill IV: separar pares e impares em buffers. Exemplo: flush quando buffer enche.
- 1253 - Caesar Cipher: deslocamento de caracteres. Exemplo: `VQREQFGT` com chave `2` -> `TOPCODER`.

HackerRank (Java):

- Java Subarray: contar subarrays com soma negativa. Exemplo: entrada curta -> total de subarrays negativos.
- Java String Reverse: validar palindromo em string. Exemplo: `madam` -> `Yes`.
- Java Anagrams: comparar strings ignorando caixa. Exemplo: `anagram` e `margana` -> `Anagrams`.

LeetCode:

- 26. Remove Duplicates from Sorted Array: dois ponteiros em array ordenado.
- 125. Valid Palindrome: string com filtro de caracteres.
- 3. Longest Substring Without Repeating Characters: janela deslizante classica.

## Exemplos de codigo por item

Revisao do tema:

- Percurso linear: `for (int n : nums) soma += n;`
- `StringBuilder`: `String invertida = new StringBuilder(s).reverse().toString();`
- Comparacao segura: `if ("ok".equals(status)) { ... }`
- Duas pontas: `while (i < j) { if (s.charAt(i++) != s.charAt(j--)) return false; }`
- Janela: `while (somaJanela > k) somaJanela -= nums[left++];`

Exercicios praticos:

- Remover duplicados: `if (nums[r] != nums[w - 1]) nums[w++] = nums[r];`
- Palindromo com limpeza: `if (!Character.isLetterOrDigit(c)) continue;`
- Primeiro nao repetido: `if (freq[c] == 1) return c;`
- Anagrama: `count[a.charAt(i)]++; count[b.charAt(i)]--;`
- Par com soma K: `if (visto.containsKey(k - x)) return true;`

Testes e checklist:

- Vazio: `assert longestSubstring("") == 0;`
- Unitario: `assert removeDuplicados(new int[]{5}) == 1;`
- Repeticao: `assert longestSubstring("bbbbb") == 1;`

Plataformas (codigo base):

- LeetCode 26: `return w; // novo tamanho`
- LeetCode 125: `String t = s.replaceAll("[^A-Za-z0-9]", "").toLowerCase();`
- LeetCode 3: `left = Math.max(left, ultimo.get(c) + 1);`

