# Paralelismo com GPU

Neste último projeto, vamos explorar os mecanismos de paralelismo multicore com GPU. Para tanto, vamos considerar a implementação da busca exaustiva que vimos, na análise realizada 
no relatório parcial, ter o desempenho bastante comprometivo quando trabalhamos com tamanhos de sequencias de DNA muito grandes.

Na busca exaustiva, existe um procedimento básico que é realizado para cada par de subsequencias que estão sendo analisadas: cálculo do score. Neste cálculo, comparamos 
posição a posição das sequencias para determinar os pesos (match, mismatch e gap) e, posteriormente, somamos todos estes pesos. A determinação do peso entre posições pode ser 
calculada de forma independente das outras posições e, portanto, é passível de paralelização. Assim, se duas sequencias S1 e S2 estiverem carregadas na GPU:

<ul>
  <li> podemos usar thrust::transform para gerar uma terceira sequencia com os pesos calculados a partir de S1 e S2
  <li> podemos usar thrust::reduce para calcular a soma dos pesos da terceira sequencia e obter o score entre S1 e S2
</ul>

O procedimento acima calcula, de maneira paralela, o score entre duas sequencias S1 e S2. Porém, quantos pares de sequencias podemos ocupar simultaneamente a GPU ? Este é o
 desafio que deverá ser resolvido neste projeto.


O que entregar:

<ul>
  <li> código-fonte da implementação exaustiva e da implementação paralela de GPU. A implementação paralela deverá seguir o cálculo do score descrito acima e, adicionalmente, 
    conter a implementação da estratégia de ocupação da GPU pelas sequencias. 
  <li> arquivos de testes utilizados
  <li> pequeno relatório descrevendo a estratégia usada para ocupação da GPU
  <li> resultados dos testes
</ul>

Um detalhe importante é que, como agora estamos trabalhando com paralelismo em GPU, os tamanhos dos arquivos de testes precisam ser bem maiores como em OpenMP. Muitas vezes, os resultados de speedup 
aparecem a partir de grandes instâncias do problema.

Caso você considere necessário, pode refatorar a sua implementação da busca exaustiva para poder explorar mais mecanismos da biblioteca TRUST em GPU.
