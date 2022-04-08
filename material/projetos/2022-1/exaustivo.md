# Busca Exaustiva para Alinhamento de Sequencias

A busca exaustiva, conforme vista aula, gera todas as soluções viáveis para um problema e, de acordo com um critério de otimalidade, elege uma
solução ótima para o problema. Especificamente para o problema de alinhamento de sequencias, ele pode ser especificado da seguinte forma:

<pre>
ALGORITMO BUSCA EXAUSTIVA
Entrada: Duas sequencias de DNA a e b
         Pesos wmat, wmis e wgap para match, mismatch e gap respectivamente
Saída: Score de um alinhamento das sequencias
       Subsequencias alinhadas

1. Gerar todas as subsequencias a´ e b´ não-nulas de a e b, respectivamente.
2. Calcular os alinhamentos de cada par de subsequencias (a´, b´) com os pesos wmat, wmis e wgap
3. Devolver o score máximo m entre os scores do passo (2) e as subsequencias associadas a ele
</pre>

Observe que, no passo (2), as subsequencias podem não ter o mesmo tamanho. Assim, não será possível calcular diretamente um score simples. Podemos usar, por exemplo:

<ul>
         <li> a estratégia vista no primeiro projeto (Alinhamento Local de Smith-Waterman) para comparar duas subsequencias
         <li> um truncamento a subsequencia maior pelo tamanho da subsequencia menor e calcular o score simples entre as duas subsequencias resultantes
         <li> o Alinhamento Local de Smith-Waterman quando as subsequencias forem diferentes e, quando forem iguais, a estratégia aleatória do Projeto II.
                  </ul> 


A partir desta descrição, nosso terceiro projeto terá duas tarefas:

<ul>
  <li> Implementar um programa C++ para ler um arquivo contendo os tamanhos de duas sequencias de DNA, seguidos das duas sequencias, uma por linha. Calcular o score máximo utilizando o algoritmo acima, assim como as subsequencias associadas a ele. 
  <li> Implementar duas estratégias diferentes para calcular os alinhamentos entre os pares de subsequencias do passo (2).

No diretório do projeto, há um gerador de entradas disponibilizado como um notebook Python. Como se trata de uma busca exaustiva, recomenda-se começar a testar com tamanhos pequenos e 
    ir aumentando gradativamente até atingir o tamanho máximo que a sua plataforma ainda consiga executar. 

