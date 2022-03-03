
# Heurística de Alinhamento Local de Smith-Waterman

Um algoritmo ingênuo para fazer o alinhamento local de duas sequencias de DNA poderia ser:

1. Gere todas as subsequências, de tamanho 1 até o tamanho total de cada sequência
2. Compare todos os pares de subsequencias, sempre escolhendo uma subsequencia de um DNA e do outro DNA, calculado seus scores
3. Escolha uma que produza o score maximal (usamos o nome maximal porque podem existir duas ou mais sequencias com score máximo)

Nao é difícil ver que este algoritmo ingênuo pode demorar muito tempo para executar quando aumentamos o tamanho das sequencias de DNA.

Uma heurística sequencial bastante interessante para reduzir o tempo de obtenção dos alinhamentos foi proposta por Smith e Waterman (1981), utilizando programação dinâmica.
Abaixo, temos a descrição do algoritmo desta estratégia:
<pre>
ALGORITMO SMITH-WATERMAN
Entrada: Duas sequencias de DNA a[i] e b[j], de tamanhos n e m respectivamente
Saída:alinhamento local

1. Inicializar H[i,0]=0, 0≤i≤n
2. Inicializar H[0,j]=0, 0≤j≤m
3. Para cada 1≤i≤n e 1≤j≤m:
4.     Calcular diagonal = H[i-1,j-1]+w(a[i],b[j]), onde w(a[i],b[j])=2 se houve match, w(a[i],b[j])=-1 se houve

</pre>
