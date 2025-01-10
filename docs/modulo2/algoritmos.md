<div style="text-indent: 2em; text-align: justify;">

<h1 style="color: #070743; font-weight: bold; text-align: center">Implementação de Algoritmos em Python</h1>

<h2 style="color: #070743; font-weight: bold; text-align: center">DFS - Viagem de IA (Busca em Profundidade)
</h2>

</div>
A busca em profundidade (Depth-First Search) explora o grafo seguindo um caminho até o final, e quando não há mais opções, volta e tenta outro caminho.

```python
def dfs_viagem(graph, inicio, destino):
    # Usando uma pilha para armazenar os nós que precisam ser visitados
    pilha = [inicio]
    
    # Dicionário para armazenar os nós visitados e o nó anterior
    visitados = {inicio: None}
    
    while pilha:
        atual = pilha.pop()
        
        if atual == destino:
            # Quando encontrar o destino, reconstrua o caminho
            return reconstruir_caminho(atual, visitados)
        
        for vizinho in graph[atual]:
            if vizinho not in visitados:
                visitados[vizinho] = atual
                pilha.append(vizinho)
    
    # Se não encontrar o destino
    return None

def reconstruir_caminho(destino, visitados):
    caminho = []
    atual = destino
    
    while atual is not None:
        caminho.append(atual)
        atual = visitados[atual]
    
    caminho.reverse()  # Inverter o caminho para que ele vá do início ao destino
    return caminho
```

**A Viagem de Sabrina:**

* **Exploração:** A busca em profundidade é como uma jornada pela rede de IA, explorando cada vez mais a fundo.
* **Transporte:** A pilha é o "transporte" de Sabrina, armazenando os nós visitados.
* **Mapa:** A variável `visitados` serve para rastrear as paradas e evitar que Sabrina se perca.
* **Objetivo:** O algoritmo explora todos os nós possíveis, sem se preocupar com o caminho mais curto.
* **Retorno:** A reconstrução do caminho permite traçar a rota completa da viagem, da origem ao destino.

**Reconstruindo a Jornada:**

* **Caminho de Volta:** Quando o destino é alcançado, Sabrina utiliza as informações da pilha para reconstruir o caminho.
* **Inversão:** O caminho é invertido para mostrar a sequência correta da viagem.

**Quando usar DFS:**

* **Exploração Completa:** Ideal para explorar todas as possibilidades em um grafo.
* **Problemas Específicos:** Útil em problemas onde a exploração completa é mais importante que a otimização.

<div style="text-indent: 2em; text-align: justify;">

<h2 style="color: #070743; font-weight: bold; text-align: center">Algoritmo de Busca com Custo Uniforme (UCS)</h2>

</div>
Algoritmo de Busca com Custo Uniforme (Uniform Cost Search - UCS). Este algoritmo é uma variação da busca em largura, onde, ao invés de explorar todos os nós com a mesma prioridade, ele explora os nós com o menor custo acumulado até aquele ponto. A ideia principal do UCS é explorar caminhos que custam menos para alcançar o objetivo, sem considerar a heurística, apenas o custo real acumulado desde o nó inicial.

**Como funciona:**

* **Expansão:** UCS sempre escolhe o nó com o menor custo acumulado para expandir.
* **Fila de Prioridade:** Organiza os nós a serem explorados com base no custo total.
* **Revisão:** Atualiza os caminhos se encontrar um caminho com custo menor.

**Detalhamento das Funções:**

* **uniform_cost_search(graph, start, goal):**
    * Recebe o grafo, o nó inicial e o objetivo.
    * Utiliza uma fila de prioridade.
    * A fila garante que o nó com menor custo seja explorado primeiro.
    * Atualiza os custos à medida que explora novos nós.
    * Reconstrói o caminho utilizando um dicionário de predecessores.

```python
import heapq

def uniform_cost_search(graph, start, goal):
    """
    Algoritmo de Busca com Custo Uniforme (UCS).
    A busca explora os nós com o menor custo acumulado até o momento.
    
    graph: Grafo representado como um dicionário onde as chaves são os nós e os valores
           são outros dicionários que representam os vizinhos e os custos de viagem.
    start: Nó inicial da busca.
    goal: Nó objetivo da busca.
    
    Retorna: O caminho encontrado entre o nó inicial e o objetivo.
    """
    
    # Fila de prioridade (min-heap) para explorar nós com o menor custo acumulado.
    open_list = []
    heapq.heappush(open_list, (0, start))  # (custo acumulado, nó)
    
    # Dicionário para armazenar os custos acumulados para cada nó.
    g_scores = {start: 0}
    
    # Dicionário para armazenar o nó predecessor de cada nó para reconstrução do caminho.
    came_from = {}
    
    while open_list:
        # Pega o nó com o menor custo acumulado da fila de prioridade.
        current_cost, current_node = heapq.heappop(open_list)
        
        # Se o nó objetivo for encontrado, reconstrua o caminho.
        if current_node == goal:
            path = []
            while current_node in came_from:
                path.append(current_node)
                current_node = came_from[current_node]
            path.append(start)  # Adiciona o nó inicial ao caminho.
            return path[::-1]  # Retorna o caminho na ordem correta.

        # Expande os vizinhos do nó atual.
        for neighbor, travel_cost in graph[current_node].items():
            tentative_cost = current_cost + travel_cost  # Calcula o custo até o vizinho.
            
            # Se o vizinho não foi explorado ou encontramos um caminho mais barato até ele.
            if neighbor not in g_scores or tentative_cost < g_scores[neighbor]:
                g_scores[neighbor] = tentative_cost
                heapq.heappush(open_list, (tentative_cost, neighbor))
                came_from[neighbor] = current_node  # Registra o nó predecessor.
    
    # Se o nó objetivo não for encontrado, retorna None.
    return None


# Exemplo de uso
graph = {
    'A': {'B': 1, 'C': 4},
    'B': {'A': 1, 'C': 2, 'D': 5},
    'C': {'A': 4, 'B': 2, 'D': 1},
    'D': {'B': 5, 'C': 1}
}

start = 'A'
goal = 'D'

path = uniform_cost_search(graph, start, goal)
print("Caminho encontrado:", path)
```

**Explicação do Código:**

* **Fila de Prioridade:** Utilizada para escolher o próximo nó a ser explorado com base no menor custo acumulado.
* **Dicionários:**
    * `g_scores`: Armazena o custo para alcançar cada nó.
    * `came_from`: Guarda o nó anterior para reconstruir o caminho.
* **Expansão de Nós:**
    * Calcula o custo para cada vizinho.
    * Atualiza o custo e adiciona à fila se o novo caminho for mais barato.
* **Reconstrução:** Reconstroi o caminho a partir do objetivo até o início.
* **Fila de Prioridade:** Garante que o caminho encontrado seja o de menor custo.

**Complexidade:**

* **Tempo:** O(E log V)
* **Espaço:** O(V + E)

**Considerações:**

* UCS é eficiente para grafos com custos variáveis.
* Não utiliza heurísticas, podendo ser mais lento em grafos grandes.