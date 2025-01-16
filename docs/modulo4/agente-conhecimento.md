<div style="text-indent: 2em; text-align: justify;">

<h4 style="color: #070743; font-weight: bold;">Considerações Iniciais</h4> 

<p>Ao iniciar o estudo sobre agentes baseados em conhecimento, minhas expectativas são compreender como esses sistemas utilizam bases de conhecimento e processos de inferência lógica para tomar decisões inteligentes. Estou particularmente interessada em como essas tecnologias podem ser aplicadas para resolver problemas reais de forma eficiente e adaptativa, especialmente em contextos onde há incerteza ou informações incompletas.

<p>Pelas aulas da matéria, entendi que agentes baseados em conhecimento funcionam como sistemas que armazenam informações em uma estrutura formal e utilizam regras lógicas para raciocinar e inferir novas conclusões. Conceitos como lógica proposicional, sintaxe, semântica e inferência foram apresentados como fundamentos essenciais para a implementação desses agentes. Também foi esclarecido como a lógica formal é aplicada para garantir que as decisões sejam racionais e consistentes.

<p>Através de exemplos como o mundo do Wumpus, percebi que o uso de regras lógicas permite que um agente analise o ambiente, preveja consequências de ações e escolha os melhores caminhos para alcançar objetivos. Esse aprendizado despertou minha curiosidade sobre as limitações e desafios, como a escalabilidade do sistema e a necessidade de representação precisa do conhecimento.

<p>Espero aprofundar meu entendimento sobre como projetar e implementar agentes baseados em conhecimento, explorando diferentes métodos de inferência e suas aplicações práticas. Meu objetivo é não apenas entender os conceitos teóricos, mas também desenvolver habilidades para aplicá-los em contextos práticos, como simulações e soluções para problemas do mundo real.

<h1 style="color: #070743; font-weight: bold; text-align: center">Agente baseado em conhecimento</h1> 
<p>Os agentes baseados em conhecimento desempenham um papel essencial na inteligência artificial (IA), utilizando uma base de conhecimento (<strong>Knowledge Base – KB</strong>) para tomar decisões racionais e fundamentadas. Eles são projetados para raciocinar sobre informações armazenadas e inferir novas conclusões, adaptando-se a diferentes cenários.</p>
<p>Os agentes baseados em conhecimento desempenham um papel essencial na inteligência artificial (IA), utilizando uma base de conhecimento (<strong>Knowledge Base – KB</strong>) para tomar decisões racionais e fundamentadas. Eles são projetados para raciocinar sobre informações armazenadas e inferir novas conclusões, adaptando-se a diferentes cenários. De acordo com <strong>Poole e Mackworth (2017)</strong>, o uso de agentes baseados em conhecimento requer uma representação formal do conhecimento, que pode ser manipulada e consultada para gerar decisões.</p>

<h3 style="color: #070743; font-weight: bold; text-align: center">Principais Conceitos de Agentes Baseados em Conhecimento</h3> 

<ul>
    <li><strong>Base de Conhecimento (KB):</strong>
        <ul>
            <li>Conjunto de sentenças que representam fatos, axiomas e regras sobre o ambiente, conforme destacado por <strong>Russell e Norvig (2021)</strong>.</li>
            <li>Sentenças expressas em linguagens formais, como lógica proposicional ou lógica de predicados, como abordado por <strong>Poole e Mackworth (2017)</strong>.</li>
        </ul>
    </li>
    <li><strong>Operações Principais:</strong>
        <ul>
            <li><strong>TELL:</strong> Adiciona novas sentenças à KB.</li>
            <li><strong>ASK:</strong> Consulta ou infere informações na KB.</li>
        </ul>
    </li>
    <li><strong>Abordagens de Construção:</strong>
        <ul>
            <li><strong>Declarativa:</strong> Inicia com uma KB vazia, sendo enriquecida progressivamente com sentenças declarativas, como sugerido por <strong>Soares (2024)</strong>.</li>
            <li><strong>Procedural:</strong> Codifica diretamente os comportamentos desejados como instruções de programa.</li>
        </ul>
    </li>
</ul>

<h3 style="color: #070743; font-weight: bold; text-align: center">Aplicações e Exemplos</h3> 

<h4 style="color: #070743; font-weight: bold;">Micromundo: Wumpus World</h4> 

<p>Um dos exemplos mais conhecidos de aplicação de agentes baseados em conhecimento é o <em>Wumpus World</em>, um modelo utilizado para exemplificar como os agentes interagem com o ambiente e tomam decisões com base nas informações que percebem. Nesse ambiente simulado:</p>
<ul>
    <li>O objetivo do agente é encontrar um tesouro, evitando cair em poços ou ser devorado pelo monstro Wumpus.</li>
    <li>Informações perceptíveis pelo agente incluem:
        <ul>
            <li><strong>Fedor:</strong> Indica proximidade do Wumpus, uma informação que pode ser armazenada na KB e consultada pelo agente ao tomar decisões, conforme discutido por <strong>Russell e Norvig (2021)</strong>.</li>
            <li><strong>Brisa:</strong> Sinaliza a presença de um poço próximo.</li>
            <li><strong>Brilho:</strong> Aponta a localização do tesouro.</li>
        </ul>
    </li>
    <li>Atividades como "mover-se", "virar" e "pegar" o tesouro são realizadas com base nas inferências do agente.</li>
</ul>

<h4 style="color: #070743; font-weight: bold;">Sistemas de Diagnóstico Médico</h4> 

<ul>
    <li>Agentes baseados em conhecimento podem identificar doenças a partir de sintomas, uma aplicação prática descrita por <strong>Poole e Mackworth (2017)</strong>.</li>
    <li>Exemplo: "Se febre alta e dor de cabeça, pode ser meningite".</li>
    <li>O mecanismo de inferência permite gerar diagnósticos precisos e recomendações médicas.</li>
</ul>

<h4 style="color: #070743; font-weight: bold;">Classificação de Qualidade do Ar</h4> 
<ul>
    <li>Agentes utilizam regras declarativas para avaliar níveis de poluentes, como apresentado por <strong>Russell e Norvig (2021)</strong>.</li>
    <li>Com base nos dados de poluição (como PM2.5), classificam a qualidade do ar em categorias como "Boa" ou "Perigosa".</li>
</ul>

<h3 style="color: #070743; font-weight: bold; text-align: center">Vantagens dos Agentes Lógicos</h3> 
<ul>
    <li><strong>Flexibilidade:</strong> Adaptação a diferentes ambientes e cenários, permitindo que o agente tome decisões baseadas em dados variáveis, como apontado por <strong>Poole e Mackworth (2017)</strong>.</li>
    <li><strong>Explicabilidade:</strong> Capacidade de justificar decisões com base na KB.</li>
    <li><strong>Inferência Dinâmica:</strong> Possibilidade de gerar novas informações em tempo real.</li>
</ul>

<h3 style="color: #070743; font-weight: bold; text-align: center">Desafios na Implementação</h3> 
<ul>
    <li><strong>Complexidade Computacional:</strong> A inferência pode ser computacionalmente intensiva em KBs grandes, como discutido por <strong>Russell e Norvig (2021)</strong>.</li>
    <li><strong>Manutenção da Consistência:</strong> Garantir que a base de conhecimento esteja livre de contradições.</li>
    <li><strong>Ambientes Parcialmente Observáveis:</strong> Nem sempre todas as informações do ambiente estão disponíveis, uma limitação destacada por <strong>Poole e Mackworth (2017)</strong>.</li>
</ul>
