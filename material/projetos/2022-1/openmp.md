# Paralelismo com OpenMP

Experimentamos, até agora, três estratégias sequenciais para o problema de alinhamento de sequencias de DNA: busca heurística, busca local e busca exaustiva.
Com os experimentos do primeiro relatório, pudemos comparar o desempenho sequencial de cada um deles. Agora vamos começar a explorar estratégias de paralelismo nos dois projetos finais.
Faremos isto com dois modelos paralelos: multicore(CPU) e manycore(GPU).

No presente projeto, exploraremos estratégias de programação multicore com OpenMP. Para tanto, você terá as seguintes tarefas:

<ul>
  <li> analisar as suas três implementações de estratégias sequenciais para identificar pontos passíveis de paralelização com OpenMP
  <li> escolher, dentre uma das três estratégias que você implementou, aquela que poderia produzir o melhor speedup com OpenMP
  <li> implementar a paralelização com OpenMP, explorando mecanismos como parallel for, parallel task, scheduling ou outro mecanismo que você tenha estudado em OpenMP
</ul>

O que entregar:

<ul>
  <li> código-fonte da implementação sequencial e da implementação paralela
  <li> arquivos de testes utilizados
  <li> pequeno relatório justificando a escolha da implementação sequencial que foi paralelizada
  <li> resultados dos testes
</ul>

Um detalhe importante é que, como agora estamos trabalhando com paralelismo, o tamanho dos arquivos de testes precisam ser bem maiores. Muitas vezes, os resultados de speedup 
aparecem a partir de grandes instâncias do problema.



