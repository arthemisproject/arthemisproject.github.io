---
title: "Algoritmos e Estruturas De Dados"
layout: default
---

# Algoritmos E Estruturas De Dados
## Sumário

1. [Algoritmo](#1-algoritmo)
- [Definição](#1-algoritmo)
- [Representações](#12-representações-de-um-algoritmo)
2. [Dados](#2-dados)
- [Tipos Primitivos](#21-tipos-primitivos)
- [Variáveis e Constantes](#22-variáveis-e-constantes)
3. [Estruturas de Controle](#3-estruturas-de-controle-e-repetição)
- [Estruturas de decisão](#31-estruturas-de-decisão)
  - [If](#if--else)
  - [Switch](#switch)
- [Estruturas de repetição](#32-estruturas-de-repetição)
  - [For](#for)
  - [While](#while)
  - [Do While](#do-while)

## 1. Algoritmo

> Um algoritmo é qualquer procedimento computacional bem definido que toma algum valor ou conjunto de valores como entrada e produz algum valor ou conjunto de valores como saída. Portanto, um algoritmo é uma sequência de etapas computacionais que transformam a entrada na saída. **(CORMEN)** 

Há três etapas que precisam ser seguidas dentro de um algoritmo:

1.  Entrada de dados
2.  Processamento de dados
3.  Saída de dados

> e.g: para calcular a área de um retângulo, precisamos seguir uma sequência finita de passos. Nesse caso, trata-se de um algoritmo matemático. Primeiro, informamos os valores da base e da altura do retângulo. Em seguida, realizamos a multiplicação desses dois valores e, então, obtemos o valor da área.

### 1.2 Representações de um algoritmo

#### 1.2.1 Fluxograma
É a representação de um algoritmo por meio de gráficos e símbolos. Cada ação é representada por uma caixa contendo a instrução do que deve ser feito. Após a execução da ação da caixa, o fluxo segue para outras ações, podendo levar a diferentes caminhos. Exemplo:

<p style="text-align: center;"><img width="300" src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/46/LampFlowchart_pt.svg/960px-LampFlowchart_pt.svg.png"></p>

#### 1.2.2 Linguagem natural

A linguagem natural é a forma de expressar a sequência de passos utilizando textos escritos em um determinado idioma, como português ou inglês. O problema é que a linguagem natural nem sempre segue uma sequência lógica rigorosa, podendo gerar ambiguidades.

## 2. Dados

> "Dados são uma coleção de fatos, números, palavras, observações ou outras informações úteis. Por meio do processamento de dados e da análise de dados, as organizações transformam dados brutos em insights valiosos que melhoram a tomada de decisões e geram resultados de negócios melhores." - [IBM](https://www.ibm.com/br-pt/think/topics/data)

### 2.1 Tipos primitivos

Os tipos primitivos representam os tipos básicos de dados utilizados em linguagens de programação.

- Inteiro -> São números pertencentes ao conjunto dos números inteiros. Podem ser positivos, negativos ou zero.

``` c
short nome_variavel = valor; 
// Ocupa 16 bits na memória.
// Variação: -32768 até 32767.

int nome_variavel = valor; 
// Ocupa 32 bits na memória.
// Variação: -2.147.483.648 até 2.147.483.647.

long nome_variavel = valor; 
// Pode ocupar 32 ou 64 bits dependendo do sistema. (Não é muito usado)
```

- Float (Real) -> São números pertencentes ao conjunto dos números reais, ou seja, números que possuem parte fracionária.

``` c
float nome_variavel = valor; 
// Ocupa 32 bits na memória.
// Precisão: até 7 dígitos decimais.

double nome_variavel = valor; 
// Ocupa 64 bits na memória.
// Precisão:15 a 16 dígitos decimais.

long double nome_variavel = valor; 
// Pode ocupar 80 ou 128 bits dependendo do sistema, permitindo maior precisão. (Isso é obscuro)
```

- Booleano (Lógico) -> Representa informações que podem assumir apenas dois valores: verdadeiro ou falso.

Em C:

``` c
#include <stdbool.h>

bool valor = true;
bool outro_valor = false;
```

Porém, ele pode ser representado por valores numericos também. Nesse caso, o valor 0 é equivalente a false, enquanto qualquer outro número (comumente 1) é tratado como true.

- Caractere -> Representa um único caractere, como letras, números ou símbolos especiais.

Exemplos de caracteres:

- Letras: `A-Z, a-z\`
- Números: `0-9\`
- Símbolos: `! @ \# % \^ &`

``` c
char letra = 'A';
char numero = '5';
char simbolo = '@';
```

### 2.2 Variáveis e Constantes

Uma variável corresponde a um espaço na memória do computador utilizado para armazenar um valor de um determinado tipo. O valor armazenado pode ser alterado durante a execução do programa. As constantes funcionam de forma semelhante, porém o valor atribuído não pode ser modificado após sua definição.

``` c
#define <NOME> <valor> // Define uma constante

<tipo> <nome> = <valor>; // Define uma variável
```

Aqui está a nova seção que você pode adicionar ao seu conteúdo:

## 3. Estruturas de Controle e Repetição

As estruturas de controle são responsáveis por definir o fluxo de execução de um algoritmo, permitindo tomar decisões e repetir ações conforme necessário.

### 3.1 Estruturas de decisão

Permitem que o algoritmo escolha diferentes caminhos com base em uma condição.

#### if / else

Executa um bloco de código caso uma condição seja verdadeira, e outro caso seja falsa.

```c
if (condicao) {
    // código executado se a condição for verdadeira
} else {
    // código executado se a condição for falsa
}
````

#### switch

Utilizado quando há múltiplas opções baseadas no valor de uma variável.

```c
switch (variavel) {
    case 1:
        // código
        break;
    case 2:
        // código
        break;
    default:
        // código padrão
}
```

### 3.2 Estruturas de repetição

Permitem executar um bloco de código várias vezes, enquanto uma condição for atendida.

#### for

Utilizado quando se sabe previamente o número de repetições.

```c
for (int i = 0; i < 10; i++) {
    // código que será repetido
}
```

#### while

Executa o bloco enquanto a condição for verdadeira.

```c
while (condicao) {
    // código
}
```

#### do while

Semelhante ao while, mas garante que o bloco seja executado pelo menos uma vez.

```c
do {
    // código
} while (condicao);
```

----

## Referencias

- CORMEN, Thomas H. et al. Algoritmos: teoria e prática. 4. ed. Rio de Janeiro: LTC, 2024. 

----

🦉 *Este material faz parte do projeto Arthemis, com foco em aprendizado colaborativo para alunos do Senac.*