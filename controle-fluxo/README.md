# DIO - Trilha Java Básico

## Controle de Fluxo - Desafio

Este repositório contém o desafio proposto no módulo de Controle de Fluxo do curso de Java Básico da [DIO](https://www.dio.me/).

### Objetivo

O objetivo deste desafio é exercitar os conceitos de controle de fluxo, utilizando laços de repetição e tratamento de exceções.

### Requisitos

O sistema deverá receber dois parâmetros via terminal que representarão dois números inteiros. Com esses dois números, o programa deve calcular a quantidade de interações (usando um loop `for`) e imprimir no console os números incrementados.

#### Exemplo:

Caso os números informados sejam `12` e `30`, o programa deve realizar 18 iterações e imprimir:

```
Imprimindo o número 1
Imprimindo o número 2
...
Imprimindo o número 18
```

Se o primeiro parâmetro for maior que o segundo, o programa deverá lançar uma exceção customizada chamada `ParametrosInvalidosException`, com a seguinte mensagem:

```
O segundo parâmetro deve ser maior que o primeiro
```

### Estrutura do Projeto

O projeto deve conter:

- A classe `Contador.java`, que contém a lógica principal do programa.
- A classe `ParametrosInvalidosException.java`, que representa a exceção customizada.

### Implementação

Segue um esboço do código para implementação:

```java
import java.util.Scanner;

public class Contador {
    public static void main(String[] args) {
        Scanner terminal = new Scanner(System.in);
        System.out.println("Digite o primeiro parâmetro");
        int parametroUm = terminal.nextInt();
        System.out.println("Digite o segundo parâmetro");
        int parametroDois = terminal.nextInt();
        
        try {
            contar(parametroUm, parametroDois);
        } catch (ParametrosInvalidosException exception) {
            System.out.println("O segundo parâmetro deve ser maior que o primeiro");
        }
    }
    
    static void contar(int parametroUm, int parametroDois) throws ParametrosInvalidosException {
        if (parametroUm >= parametroDois) {
            throw new ParametrosInvalidosException();
        }
        
        int contagem = parametroDois - parametroUm;
        for (int i = 1; i <= contagem; i++) {
            System.out.println("Imprimindo o número " + i);
        }
    }
}
```

Classe da exceção customizada:

```java
public class ParametrosInvalidosException extends Exception {
    public ParametrosInvalidosException() {
        super("O segundo parâmetro deve ser maior que o primeiro");
    }
}
```

### Como Executar

1. Clone este repositório
2. Compile o código usando um compilador Java (JDK instalado)
3. Execute o programa e forneça os parâmetros solicitados

## 🔗 Contato

[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)][linkedin]

Projeto desenvolvido como parte do treinamento da DIO.

[linkedin]: https://www.linkedin.com/in/heitor-augusto-dev