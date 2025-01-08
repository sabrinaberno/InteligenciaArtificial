<div style="text-indent: 2em; text-align: justify;">

<h1 style="color: #070743; font-weight: bold; text-align: center">Consistência em Problemas de Satisfação de Condições (CSP)</h1> 

A consistência em CSPs (Problemas de Satisfação de Restrições) é fundamental para otimizar a busca por soluções válidas, reduzindo o espaço de busca e garantindo que as atribuições de valores respeitem as restrições do problema. A seguir, exploraremos os conceitos de consistência aplicados aos nós, arcos, trajetos, k-consistência e condições globais.

<h3 style="color: #070743; font-weight: bold; text-align: center;">Consistência de Nós</h3>

<p>Um nó em um CSP representa uma variável associada a um domínio de valores. Diz-se que uma variável é <strong>nó-consistente</strong> se todos os valores em seu domínio satisfazem suas restrições unitárias (aquelas que envolvem apenas a própria variável). De acordo com Dechter (2003), a consistência de nós permite a eliminação de valores inviáveis de maneira isolada, antes de considerar interações com outras variáveis.</p>

<p>Por exemplo, se a variável X tem domínio {1, 2, 3} e uma restrição que exige X > 1, então, após a verificação de consistência, o domínio será reduzido para {2, 3}. Quando todos os nós de um grafo são consistentes, o grafo é considerado <strong>nó-consistente</strong>, facilitando a busca inicial por soluções ao remover valores obviamente inválidos.</p>

<h3 style="color: #070743; font-weight: bold; text-align: center;">Consistência de Arco</h3>

<p>A consistência de arco verifica restrições binárias entre pares de variáveis conectadas por um arco no grafo que representa o problema. Diz-se que duas variáveis são <strong>arco-consistentes</strong> se, para cada valor em uma delas, existe pelo menos um valor correspondente na outra que satisfaça a restrição entre elas (Russell & Norvig, 2016).</p>

<p>Por exemplo, considere as variáveis X e Y com restrição \(Y = X^2\). Se o domínio de X for {0, 1, 2, 3}, a consistência de arco exigirá que o domínio de Y seja reduzido para {0, 1, 4, 9}, garantindo que todos os valores em X tenham correspondentes válidos em Y.</p>

<p>Algoritmos como o AC-3 são amplamente utilizados para garantir a consistência de arco, eliminando valores incompatíveis e reduzindo o espaço de busca (Dechter, 2003).</p>

<h3 style="color: #070743; font-weight: bold; text-align: center;">Consistência de Trajeto</h3>

<p>A consistência de trajeto vai além de pares de variáveis, estendendo a análise para trios ou grupos maiores. Três variáveis X, Y, Z são consideradas <strong>trajeto-consistentes</strong> se, para qualquer valor consistente entre X e Y, e entre X e Z, há pelo menos um valor em Z que mantém a consistência (Poole & Mackworth, 2017).</p>

<p>Por exemplo, considere as restrições \(X + Y = 10, X + Z = 15\) e os domínios \(X = \{5, 10\}\), \(Y = \{5, 10\}\), \(Z = \{5, 10\}\). A consistência de trajeto verificará que, para \(X = 5\), \(Y = 5\) satisfaz \(X + Y\), mas requer \(Z = 10\) para satisfazer \(X + Z\). A consistência de trajeto permite reduzir ainda mais os domínios, considerando implicações em múltiplas variáveis.</p>


<h3 style="color: #070743; font-weight: bold; text-align: center;">Consistência K</h3>

<p>A k-consistência é uma generalização da consistência de trajeto para conjuntos maiores de variáveis. Um CSP é k-consistente se, para qualquer atribuição consistente de k - 1 variáveis, existe uma atribuição consistente para a k-ésima variável (Frühwirth, 1998). Além disso, um CSP é fortemente k-consistente se for k-consistente para todos os valores de k até o número total de variáveis.</p>

<p>Por exemplo, em um problema com três variáveis X, Y, Z, a 3-consistência garante que, se X = 1 e Y = 2 são consistentes, será possível atribuir um valor consistente a Z.</p>

<h3 style="color: #070743; font-weight: bold; text-align: center;">Consistência Global</h3>

<p>A consistência global, como destacado por Russell e Norvig (2016), considera todas as restrições do problema simultaneamente. Um grafo é globalmente consistente se for k-consistente para todo k, garantindo que qualquer subconjunto de variáveis possa ser atribuído de maneira consistente sem violar as restrições.</p>

<p>A consistência global pode ser alcançada por técnicas como propagação de limites, que identifica e remove valores inconsistentes de maneira eficiente, evitando a verificação exaustiva de todas as combinações possíveis (Poole & Mackworth, 2017).</p>

