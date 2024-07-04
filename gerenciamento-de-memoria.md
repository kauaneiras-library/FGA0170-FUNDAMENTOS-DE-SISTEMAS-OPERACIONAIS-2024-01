# Gerenciamento de Memória
Um sistema operacional tem um componente central chamado gerenciador de memória. Esse gerenciador é responsável por decidir onde na memória será colocado o código de um novo processo (programa) que está sendo carregado de um arquivo armazenado em um dispositivo de entrada e saída (como um HD).

### Vazamento de Memória (Memory Leak)

**Vazamento de memória** ocorre quando a memória que foi alocada (reservada) pelo programa não é liberada corretamente, mesmo quando não é mais necessária. Existem duas situações principais para o vazamento de memória:

1. **Memória Alocada, mas Inacessível:**
   - Blocos de memória são alocados e prontos para serem usados pelo programa.
   - Porém, esses blocos não são acessíveis porque a aplicação perdeu a referência a eles (não há ponteiros apontando para essa área de memória).
   - Isso significa que, embora a memória esteja reservada, ela não pode ser usada pelo programa nem por outros processos, ficando “preso” e inacessível.

2. **Memória Ainda Referenciada, mas Inutilizável:**
   - Blocos de memória contêm dados que poderiam ser liberados porque não são mais necessários.
   - Contudo, devido a um "esquecimento" no código, esses blocos ainda são referenciados (ou seja, o programa ainda mantém ponteiros para eles).
   - Mesmo que esses blocos não estejam sendo usados, eles não podem ser liberados enquanto houver referências a eles.

### Classes de Gerenciadores de Memória

Os gerenciadores de memória podem ser divididos em duas classes:

1. **Swapping:**
   - Alternam os processos entre a memória principal e o disco durante a execução.
   - Usado para gerenciar a memória de forma eficiente quando a memória RAM é limitada.

2. **Sem Swapping:**
   - Não alternam processos entre a memória principal e o disco.
   - Nosso foco está nessa classe, que é a mais utilizada há muito tempo.

### Resumo

O vazamento de memória é um problema porque a memória fica reservada e não pode ser usada para outras tarefas, reduzindo a eficiência do sistema. Entender como a memória é gerenciada e como evitar vazamentos é crucial para manter o bom desempenho de um sistema operacional.
