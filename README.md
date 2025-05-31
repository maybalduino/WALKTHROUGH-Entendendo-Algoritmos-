# Walkthrough 

## 📚 Documentação

[Entendendo Algoritmos - Aditya Y. Bhargava](https://www.amazon.com.br/Entendendo-Algoritmos-Ilustrado-Programadores-Curiosos/dp/8575225634)

## Pesquisa Binária

Imagine que ao fazer um login em um site, o site precisa verificar que você tem uma conta cadastrada. Logo, ele começa uma busca pelo seu nome de usuário em ma banco de dados. Digamos que seu usuário seja maybaldwin. O site poderia começar pelos As e procurar até o M, porém faz mais sentido que ele comece a busca pelo meio. Que nem fazíamos na escola com um dicionário para agilizar a procura. 

Isto é um **problema de busca** e em todos esses casos usam um algoritmo para resolvê-lo chamado **PESQUISA BINÁRIA**.

💊 *A pesquisa binária é um algoritmo que tem como entrada uma **lista ordenada** de elementos. Se o elemento que você está buscando está na lista, a pesquisa binária retorna a sua localização. Senão, a pesquisa retorna None.*

- Imagine que em uma lista ordenada de 1 a 100, você precisa advinhar em qual o número estou pensando, a cada número te digo se é maior ou menor do que o escolhido. Se começar pela ordem, você irá gastar 99 tentativas caso o número correto fosse 99. O nosso objetivo é que gastar o menor número possíveis de tentativas.

    |~1~| 2 | ... | 99 | 100 |
    |---|---|-----|----|-----|
     
     Usando o conceito da busca no dicionário mencionado anteriormente, vamos otimizar essa busca começando pelo número 50, ou seja pelo meio da lista. Como 99 é maior que 50, já eliminamos 50 números a serem chutados.
    | ~1~ | ... | ~49~ | ~50~ | 51 | ... | 98 | 99 | 100 |
    |---|-----|----|----|----|-----|----|----|-----|

    Com a busca binária **você chuta um número intermediário e elimina a metade dos itens restantes a cada vez.** 
    
    | 100 itens | 50 | 25 | 13 | 7 | 4 | 2 | 1 | 
    |--------|----|----|----|---|---|---|---|
    
    🎯 **7 Etapas/Tentativas**

💡 **Para uma lista de n números, a pesquisa binária precisa de log2 n para retornar o valor correto, enquanto uma pesquisa simples precisa de n etapas.**
