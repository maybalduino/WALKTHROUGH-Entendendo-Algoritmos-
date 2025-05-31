
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

*Não precisa ir atrás do seu livro de ensino médio para procurar logaritmos. É só pensar na seguinte lógica: na expressão log10 100, "quantos 10s conseguimos multiplicar para chegar a 100?" A resposta é 2 pois 10x10=100.*

```python
    def pesquisa_binaria(lista, item):
        
        baixo = 0
        alto = len(lista) - 1

        while baixo <= alto:
            meio = (baixo + alto)/2
            chute = lista[meio]
            if chute == item:
                return meio
            if chute > item:
                alto = meio - 1
            else:
                baixo = meio + 1
        return None
    minha_lista = [1,3,5,7,9]

    print pesquisa_binaria(minha_lista, 3) # =>1 Lembre q a lista começa no indice 0

    print pesquisa_binaria(minha_lista, -1) # =>None
```

### 📝 Exercícios

- Suponha que você tenha uma lista com 128 nomes e esteja fazendo uma pesquisa binária. Qual seria o número máximo de etapas que você levaria para encontrar o nome desejado?

    *Como vimos anteriormente, em uma pesquisa binária precisamos de log2 n etapas, aonde n é o tamanho da lista ordenada.
    log 128 = 7. Logo levaria no máximo 7 tentativas.*

- Suponha que você duplique o tamanho da lista. Qual seria o número máximo de etapas agora?

    *log 256 = 8 etapas.*
