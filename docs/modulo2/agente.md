<div style="text-indent: 4em; text-align: justify;">


<h4 style="color: #070743; font-weight: bold;">Considerações Iniciais</h4> 

<p>O tema dos agentes de solução de problemas na inteligência artificial desperta grande interesse, pois apresenta um equilíbrio entre teoria e aplicação prática. Antes de aprofundar no assunto, as aulas da matéria proporcionaram uma visão inicial sobre como esses agentes funcionam como componentes essenciais para resolver problemas em ambientes complexos e dinâmicos. Até o momento, entendi que eles operam com base na formulação de objetivos e problemas, executando estratégias de busca e planejamento para alcançar resultados otimizados. Essa abordagem me ajudou a compreender a importância de conceitos como estados, ações, algoritmos de busca e heurísticas, frequentemente utilizados em aplicações como jogos, sistemas de recomendação e robótica.

<p>Minhas expectativas são de consolidar esse conhecimento inicial, explorando de forma mais detalhada como diferentes modelos e algoritmos podem ser aplicados a problemas reais. Espero também entender melhor a escolha entre busca informada e não informada, assim como as vantagens e limitações de cada abordagem em cenários diversos. Por fim, estou curiosa para aprofundar a análise dos algoritmos genéticos e sua contribuição na resolução de problemas mais complexos. Acredito que esse estudo permitirá conectar a teoria com situações práticas, oferecendo um panorama mais completo e aplicável dos agentes de solução de problemas na inteligência artificial.

<br>
<br>

<h1 style="color: #070743; font-weight: bold; text-align: center">Agente de Soluções de Problemas</h1> 

Um agente de soluções de problemas é um componente central no estudo da inteligência artificial, projetado para lidar com situações onde a sequência de ações necessária para alcançar um objetivo não é evidente de imediato (RUSSELL; NORVIG, 2016). Esse tipo de agente é capaz de "planejar à frente" ao considerar uma sequência de ações que o conduza ao estado desejado, ou seja, eles analisam o ambiente, formulam problemas e utilizam estratégias de busca para encontrar a melhor solução, sendo fundamentais em cenários como planejamento, navegação e jogos estratégicos. Essa capacidade de previsão é essencial em ambientes determinísticos e completamente observáveis, onde o agente pode confiar em seu modelo do mundo para alcançar resultados específicos.

<h3 style="color: #070743; font-weight: bold; text-align: center">Estrutura de Funcionamento
</h3> 

O processo de resolução de problemas por agentes pode ser dividido em quatro etapas principais segundo Russell e Norvig (2016) no livro Artificial Intelligence: A Modern Approach:

<ol>
    <li><strong>Formulação do Objetivo:</strong> Identificação de um estado final desejado, que orienta as ações do agente. Por exemplo, um turista em Roma pode definir como objetivo chegar a Londres.</li>
    <li><strong>Formulação do Problema:</strong> Modelagem abstrata do mundo, considerando estados possíveis e ações disponíveis. Nesse caso, as cidades podem representar os estados e os meios de transporte, como trem ou avião, podem ser as ações disponíveis. Para viajar de Roma a Londres, as opções podem incluir um voo direto ou trens com conexões.</li>
    <li><strong>Busca de Solução:</strong> UUtilização de algoritmos para encontrar um caminho viável do estado inicial ao estado objetivo. Por exemplo, para ir de Edimburgo a Londres, o agente pode explorar as opções de trem direto ou voos com menor tempo de viagem. A escolha da solução pode levar em consideração fatores como custo, tempo ou conveniência.</li>
    <li><strong>Execução da Solução:</strong> Implementação da sequência de ações planejada, como reservar passagens, viajar até a estação de trem ou aeroporto, embarcar no transporte escolhido e, finalmente, chegar a Londres.</li>
</ol>

Esses agentes são amplamente aplicados em diversas áreas, como:
<ol>
    <li> <strong>Robótica:</strong> Planejamento de trajetórias para movimentação eficiente </li>
    <li> <strong>Sistemas de logística:</strong> Otimização de rotas de entrega.</li>
    <li><strong> Jogos:</strong> Definição de estratégias vencedoras em jogos como xadrez.</li>
    <li><strong> Sistemas de recomendação:</strong> Sugestões personalizadas baseadas em padrões de busca.</li>

<h3 style="color: #070743; font-weight: bold; text-align: center">Modelos de Busca e Algoritmos </h3> 
<p>Agentes de soluções de problemas operam em ambientes representados por grafos de estados, onde os vértices simbolizam estados possíveis e as arestas correspondem às ações disponíveis (RUSSELL; NORVIG, 2016). As estratégias de busca podem ser divididas em:</p>

<ul>
    <li><strong>Busca não-informada:</strong> Exploração sistemática do espaço de estados sem informações adicionais sobre a proximidade do objetivo.</li>
    <li><strong>Busca informada:</strong> Utilização de heurísticas para priorizar estados mais promissores, tornando a busca mais eficiente.</li>
</ul>

<p>Esses agentes são ideais para resolver problemas complexos que demandam uma análise profunda de alternativas, diferentemente dos agentes reativos, que operam com base em regras de condição-ação (ALGORITMOZ, 2020). O agente recebe a formulação do problema e o objetivo, busca a sequência de ações necessárias e as executa.</p>

<p>Um exemplo clássico é o problema "Férias na Romênia", em que o objetivo é sair de Arad e chegar a Bucareste. Nesse caso, as cidades representam os estados e as estradas, as ações. O problema é formulado considerando os elementos essenciais:</p>

<ul>
    <li><strong>Estado inicial:</strong> Arad.</li>
    <li><strong>Ações possíveis (função sucessora):</strong> Conexões entre cidades.</li>
    <li><strong>Teste de objetivo:</strong> Verificação de chegada a Bucareste.</li>
    <li><strong>Custo do caminho:</strong> Distâncias percorridas.</li>
</ul>

<p>A solução ótima é aquela que minimiza o custo do caminho, utilizando uma abstração do mundo real representada por um grafo de estados, desempenhando um papel crucial na IA, permitindo resolver problemas complexos de forma eficiente e otimizada (ALGORITMOZ, 2020). Essa abordagem é fundamental para os agentes de soluções de problemas, como detalhado no vídeo “Introdução à IA #6: Agentes de Resolução de Problemas” (ALGORITMOZ, 2020). </p>

No contexto da inteligência artificial, o algoritmo utilizado para resolver o problema do mundo do aspirador e o problema do caixeiro viajante (TSP) segue abordagens específicas, baseadas em estratégias de busca e otimização (RUSSELL; NORVIG, 2016).

</div>