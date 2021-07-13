# Laboratorio2

Paula Adriana Alves Sousa - 1947923

EXERCÍCIO 10

Para o exercício 10 o intuito era fazer a multiplicação de números com 16 bits.
Desta forma, foram inicializados dois registradores com um valor X e executada a seguinte subrotina:

Em um loop, verificamos se R1 é zero, pois como a partir dos deslocamentos à direita (que serão em breve executados), o
final deste código se dará quando R1 zerar.
Por isso, se R1 = 0, fazemos um salto para o final do programa com o comando jumpm.

R1 é deslocado 1 vez â direita.
Só é somado se o menor bit significativo for 1, 
então caso a flag carry do registrador esteja setada, o programa executa a soma R2 = R2 + R0 e retorna, 
se não, 
R0 é deslocado 1 vez à esquerda e o loop recomeça.


EXERCÍCIO 11

Para o exercício 11 foi demandado que calculássemos o fatorial, alterando, no final do programa, apenas um registrador. 
Além de verificar se o fatorial daria mais que 32 bits.

Para isso foi feita mais uma subrotina.

Separando o código em 4 partes temos que:

1) Para não alterarmos os valores finais dos registradores colocamos os valores deles numa pilha antes de iniciarmos 
a subrotina e pegamos de volta seus valores dela no fim do código.

2)Para verificarmos se o fatorial deu um número maior que 32 bits obtivemos o auxílio da flag. Assim quando BXVS é
setada, R2 recebe -1, voltamos para o main e R0 recebe R2.

3) Para calcularmos o fatorial executamos uma sequência de comandos matemáticos disponíveis em assembly:
Guardamos o valor de R0 em R2, no loop da subrotina R1 recebe R0 menos um e o multiplicador/R2 recebe mul/R2 vezes R1.

Se R1 for igual a zero saímos do loop e voltamos para o main, 
pois 2 é o menor valor a ser multiplicado em qualquer número maior que 2.
Se não o loop da subrotina continua.

4) Caso R0 seja 1, o valor retornado para o main é 1.


