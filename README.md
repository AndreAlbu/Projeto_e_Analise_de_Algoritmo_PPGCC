# Análise de Algoritmos para Detecção de Fraudes em Transações Financeiras

### Descrição do Problema

9 - Fraudes em Transações Financeiras

Contexto: Identificar rapidamente três transações cujos valores somam exatamente um valor de entrada.

Problema: Vetores de valores de transações com 10³ a 10⁵ valores.

Algoritmos a comparar:

9.1) Verificação ingênua O(n³).

9.2) Algoritmo com ordenação + divisão e conquista.

Experimento sugerido:

Gerar vetores aleatórios de preços.

Medir tempo médio.

## Pseudocódigo dos Algoritmos

### Algoritmo Ingênuo — O(n³)

```python

função tres_somas_ingenuo(vetor, alvo):

  n ← tamanho de vetor

  para i de 0 até n−1:

    para j de i+1 até n−1:

      para k de j+1 até n−1:

        se vetor[i] + vetor[j] + vetor[k] = alvo:

            retornar (vetor[i], vetor[j], vetor[k])

  retornar nulo
```

### Algoritmo Otimizado com Ordenação e Dois Ponteiros — O(n²)

```python

função tres_somas_otimizado(vetor, alvo):

  arr ← vetor ordenado
  n ← tamanho de arr

  para i de 0 até n−3:

    alvo2 ← alvo − arr[i]
    l ← i + 1
    r ← n − 1

    enquanto l < r:

      soma ← arr[l] + arr[r]

      se soma = alvo2:

        retornar (arr[i], arr[l], arr[r])

      se soma < alvo2:

        l ← l + 1

      senão:

        r ← r − 1

  retornar nulo
```

## Experimento 1

O Experimento 1 tem como objetivo comparar o desempenho dos algoritmos de três somas na faixa de entrada em que ambos ainda são executáveis em tempo viável. Para isso, foram gerados vetores de tamanhos variando de 1.000 a 10.000 elementos, com incrementos de 500 unidades. Para cada tamanho, foram realizadas dez repetições independentes, cada uma consistindo em:

1. Geração de um vetor de transações com valores inteiros aleatórios.

2. Seleção aleatória de três posições do vetor para construção de um alvo garantidamente alcançável.

3. Execução do algoritmo ingênuo e medição do tempo necessário para encontrar a trinca correspondente.

Execução do algoritmo otimizado sobre o mesmo vetor e alvo, também com registro do tempo de execução.

Após as repetições, foi calculada a média dos tempos obtidos para cada algoritmo em cada tamanho de entrada. Os resultados foram organizados em uma tabela e utilizados para compor o gráfico comparativo entre o crescimento empírico das abordagens O(n³) e O(n²) no intervalo de entrada em que ambas podem ser observadas de forma completa.

#### Resultado Experimento 1
grafico e tabela?

## Experimento 2

O Experimento 2 tem como finalidade avaliar o comportamento do algoritmo otimizado em escalas maiores de entrada, alcançando tamanhos de vetor incompatíveis com a execução do algoritmo ingênuo em tempo razoável. Para isso, foram considerados vetores com tamanhos variando de 1.000 a 100.000 elementos, utilizando incrementos de 5.000 unidades. Em cada tamanho, foram conduzidas dez repetições independentes seguindo o mesmo procedimento experimental:

1. Geração de um vetor de transações com valores inteiros aleatórios.

2. Seleção aleatória de três posições distintas para definir um alvo garantido de ser encontrado pelo algoritmo.

3. Execução do algoritmo otimizado e medição precisa do tempo de processamento até a obtenção da trinca correspondente.

Os tempos individuais foram acumulados e posteriormente normalizados pela média de dez execuções para cada tamanho de entrada. Os resultados foram reunidos em uma tabela e utilizados na construção de um gráfico que ilustra o crescimento empírico do algoritmo otimizado até 100.000 elementos, permitindo observar sua evolução prática dentro do regime O(n²).

#### Resultado Experimento 2
grafico e tabela?
