<div style="text-indent: 2em; text-align: justify;">

<h1 style="color: #070743; font-weight: bold; text-align: center">Algoritmos de Busca: Busca Cega e Busca Informada</h1>

Os algoritmos de busca são amplamente utilizados para a solução de problemas em sistemas de inteligência artificial. Eles consistem na exploração de espaços de estados para encontrar uma solução a partir de um estado inicial até um estado objetivo. As abordagens de busca podem ser classificadas em dois tipos principais: busca cega (uninformed search) e busca informada (informed search). (BARROS, 2006)

<h3 style="color: #070743; font-weight: bold; text-align: center">1. Agente de Solução de Problemas</h3>

Um agente que resolve problemas por meio de busca passa pelas seguintes etapas (NILSSON, 1980):
    <ol>
        <li><strong>Formulação de objetivo:</strong> o agente define um ou mais objetivos a serem alcançados.</li>
        <li><strong>Formulação de problema:</strong> o agente descreve os estados e ações necessárias para atingir o objetivo.</li>
        <li><strong>Busca:</strong> antes de executar ações, o agente simula sequências de ações em um modelo de estados.</li>
        <li><strong>Execução:</strong> as ações definidas na etapa de busca são realizadas para atingir o estado objetivo.</li>
    </ol>
Esses agentes atuam em ambientes determinísticos ou não determinísticos, podendo operar em malha aberta ou malha fechada, dependendo da capacidade de obter feedback do ambiente durante a execução (RUSSELL; NORVIG, 2010).

<h3 style="color: #070743; font-weight: bold; text-align: center">2. Busca Cega (Uninformed Search)</h3>

A busca cega, também chamada de busca não informada, é uma estratégia onde o agente não possui nenhuma informação adicional sobre a distância até o objetivo, exceto os estados e as ações possíveis a partir de cada estado. Ela explora o espaço de estados de forma sistemática, sem orientação específica (BARROS, 2010).


<ul>
        <li><strong>Busca em largura (Breadth-First Search – BFS):</strong> explora todos os nós de um nível antes de avançar para o próximo. 
            É completa e encontra a solução de menor custo, desde que todas as ações tenham custo uniforme. (NILSSON, 1980)
            <ul>
                <li><strong>Completude:</strong> sim</li>
                <li><strong>Complexidade de tempo:</strong>O(b^d)</li>
                <li><strong>Complexidade de espaço:</strong>O(b^d)</li>
            </ul>
        </li>
        <li><strong>Busca em profundidade (Depth-First Search – DFS):</strong> explora o caminho até o nível mais profundo antes de retroceder. 
            É mais eficiente em termos de memória, mas não é completa para espaços infinitos e pode não encontrar a solução de menor custo. (BARROS, 2010)
            <ul>
                <li><strong>Completude:</strong> não, em espaços infinitos</li>
                <li><strong>Complexidade de tempo:</strong> O(b^m)</li>
                <li><strong>Complexidade de espaço:</strong> O(bm)</li>
            </ul>
        </li>
    </ul>

<h3 style="color: #070743; font-weight: bold; text-align: center">3. Busca Informada (Informed Search)</h3>

<p>
    A busca informada, ou <strong>heurística</strong>, utiliza informações adicionais sobre o problema para guiar a busca em direção ao objetivo 
    de forma mais eficiente. Essa informação é fornecida por uma função heurística \( h(n) \), que estima o custo para atingir o objetivo 
    a partir do estado atual (RUSSELL; NORVIG, 2010).
</p>

<h4 style="color: #070743; font-weight: bold; text-align: center">Principais algoritmos de busca informada</h4>

<ul>
    <li><strong>Busca gulosa (Greedy Best-First Search):</strong> expande o nó que parece mais promissor de acordo com a função heurística. 
        Embora rápida, não é completa nem ótima em todos os casos. (BARROS, 2010)
        <ul>
            <li><strong>Completude:</strong> não, em todos os casos</li>
            <li><strong>Otimização de custo:</strong> não garante a solução de menor custo</li>
        </ul>
    </li>
    <li><strong>Busca A*:</strong> combina a busca de custo uniforme e a busca gulosa, utilizando uma função de avaliação \( f(n) = g(n) + h(n) \), 
        onde \( g(n) \) é o custo do caminho até o nó \( n \) e \( h(n) \) é a estimativa heurística do custo restante. 
        A busca A* é completa e ótima se a heurística for admissível. (RUSSELL; NORVIG, 2010)
        <ul>
            <li><strong>Completude:</strong> sim</li>
            <li><strong>Otimização de custo:</strong> sim, se \( h(n) \) for admissível</li>
        </ul>
    </li>
</ul>
    
<h3 style="color: #070743; font-weight: bold; text-align: center"> 4. Comparação: Busca Cega vs. Busca Informada</h3>

<table style="width: 100%; border-collapse: collapse; text-align: center;">
    <tr style="background-color: #f0f0f0;">
        <th>Critério</th>
        <th>Busca Cega</th>
        <th>Busca Informada</th>
    </tr>
    <tr>
        <td>Uso de informação</td>
        <td>Não utiliza informações adicionais</td>
        <td>Utiliza funções heurísticas</td>
    </tr>
    <tr>
        <td>Eficiência</td>
        <td>Menor eficiência</td>
        <td>Maior eficiência</td>
    </tr>
</table>

<h3 style="color: #070743; font-weight: bold">4.1 Mundo do Aspirador </h3> 

<p>O <b>problema do mundo do aspirador</b> é um exemplo clássico de problema de busca e planejamento, onde um agente (aspirador) deve limpar um conjunto de células em uma grade, movendo-se entre elas. O ambiente é geralmente representado por uma grade 2D, onde algumas células estão sujas e outras limpas. O agente tem a capacidade de se mover para direções específicas (como norte, sul, leste e oeste) e limpar a célula em que se encontra, enquanto tenta alcançar o objetivo de limpar todas as células do ambiente.</p>

<p>A solução para esse problema pode ser implementada com um algoritmo de busca como a <b>busca em largura (breadth-first search)</b> ou a <b>busca em profundidade (depth-first search)</b>, dependendo da complexidade e dos requisitos de eficiência. Para um ambiente simples e pequeno, a busca em profundidade pode ser suficiente, onde o agente explora recursivamente suas opções, movendo-se até uma célula limpa e depois retornando se necessário.</p>

<p>Uma abordagem mais sofisticada seria a utilização de <b>algoritmos de planejamento</b>, que consideram as ações do aspirador como parte de uma sequência planejada de tarefas. O <b>algoritmo de busca A* (A-star)</b> pode ser utilizado aqui, já que ele é eficiente para encontrar o caminho mais curto considerando uma heurística que aproxima a distância do estado atual até o estado objetivo (todas as células limpas). Nesse caso, a função de custo pode ser baseada no número de células que o aspirador precisa limpar, enquanto a heurística pode estimar o número de células sujas restantes.</p>


<h3 style="color: #070743; font-weight: bold">4.2 Problema do Caixeiro Viajante (TSP) </h3> 

<p>O <b>problema do caixeiro viajante (TSP)</b> é um clássico problema de otimização, no qual o objetivo é encontrar o caminho mais curto que permita a um vendedor visitar um conjunto de cidades e retornar à cidade de origem. O TSP é um problema NP-difícil, o que significa que sua solução exata leva um tempo exponencial em relação ao número de cidades, tornando-o impraticável para grandes conjuntos de cidades. Por esse motivo, soluções aproximadas e heurísticas são frequentemente usadas.</p>

<p>Uma das abordagens mais comuns para resolver o TSP é o <b>algoritmo de força bruta</b>, que gera todas as possíveis permutações das cidades e calcula o custo total de cada uma, selecionando a sequência que resulta no menor custo. Esse método é eficaz para um número pequeno de cidades, mas se torna extremamente lento à medida que o número de cidades cresce, já que o número de permutações possíveis é fatorial (n!).</p>

<p>Uma alternativa mais eficiente é o uso de <b>algoritmos de busca local</b>, como o <b>algoritmo de troca 2-opt</b>. Esse método começa com uma solução inicial (por exemplo, uma sequência aleatória de cidades) e tenta melhorar essa solução trocando pares de cidades em sua ordem. Se a troca resultar em um caminho de menor custo, ela é mantida, e o processo é repetido até que não haja mais melhorias possíveis.</p>

<p>Além disso, algoritmos como <b>algoritmos genéticos, simulated annealing e algoritmos de colônia de formigas</b> também são aplicados ao TSP. Esses métodos buscam encontrar boas soluções aproximadas em um tempo razoável. No caso do <b>algoritmo genético</b>, uma população de soluções potenciais é evoluída ao longo do tempo através de operações como cruzamento e mutação, sempre selecionando as soluções com menor custo para formar a próxima geração.</p>

<p>Por fim, para problemas de TSP com muitas cidades, as soluções exatas se tornam inviáveis, e, por isso, a abordagem mais comum é o uso de <b>heurísticas e metaheurísticas</b>, que garantem encontrar soluções boas em tempo razoável, embora não necessariamente ótimas.</p>

<br>
<br>
<br>
Em ambos os problemas — o mundo do aspirador e o caixeiro viajante — os algoritmos de busca e otimização desempenham um papel fundamental. O mundo do aspirador utiliza algoritmos de busca como a busca em largura e A*, enquanto o TSP, por ser mais complexo, é abordado com técnicas como força bruta para problemas pequenos e algoritmos de otimização aproximada (como 2-opt e algoritmos genéticos) para cenários mais desafiadores e com muitas cidades. Ambos os problemas exemplificam como a inteligência artificial pode ser aplicada para resolver tarefas de planejamento e otimização em ambientes controlados e do mundo real.

