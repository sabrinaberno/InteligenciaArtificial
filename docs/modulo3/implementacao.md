<div style="text-indent: 2em; text-align: justify;">

<h1 style="color: #070743; font-weight: bold; text-align: center">Implementação dos Algoritmos</h1> 

 <p>Este exemplo utiliza um algoritmo genético para resolver o problema de agendamento de aluguel de quadras de pickleball, onde o objetivo é alocar quadras e horários para diferentes grupos de jogadores, garantindo que:</p>
<ul>
    <li>Nenhuma quadra seja usada por mais de um grupo ao mesmo tempo.</li>
    <li>Cada grupo respeite as restrições de disponibilidade das quadras e dos jogadores.</li>
</ul>

<h3 style="color: #070743; font-weight: bold; text-align: center;">Definição do Problema</h3>
<p>No problema, temos as seguintes variáveis:</p>
<ul>
    <li><strong>Quadras:</strong> Quadra 1, Quadra 2, Quadra 3</li>
    <li><strong>Horários:</strong> 9:00-10:00, 10:00-11:00, 11:00-12:00</li>
    <li><strong>Grupos:</strong> Grupo A, Grupo B, Grupo C, Grupo D</li>
</ul>

<p>Os grupos têm restrições sobre quais quadras e horários estão disponíveis. A solução busca alocar cada grupo em uma quadra e horário disponíveis, respeitando as restrições.</p>

<h3 style="color: #070743; font-weight: bold; text-align: center;">Exemplo de Execução</h3>

<p>Após executar o algoritmo genético, a solução final é apresentada, onde cada grupo está alocado em uma quadra e horário válidos:</p>

<pre>

Grupo A: Quadra 1 às 9:00-10:00
Grupo B: Quadra 2 às 10:00-11:00
Grupo C: Quadra 3 às 11:00-12:00
Grupo D: Quadra 1 às 10:00-11:00
</pre>

<p>O algoritmo genético continua iterando até que uma solução válida seja encontrada ou o número máximo de gerações seja alcançado.</p>
</div>

```python
import random

# Parâmetros do Algoritmo Genético
POPULATION_SIZE = 500
MUTATION_RATE = 0.1
GENERATIONS = 1000

# Problema de Agendamento de Quadras
AVAILABILITY = {
    "Quadra 1": ["9:00-10:00", "10:00-11:00", "11:00-12:00"],
    "Quadra 2": ["9:00-10:00", "10:00-11:00", "11:00-12:00"],
    "Quadra 3": ["9:00-10:00", "10:00-11:00", "11:00-12:00"]
}

GROUPS = ["Grupo A", "Grupo B", "Grupo C", "Grupo D"]

# Função para criar uma solução inicial aleatória
def create_individual():
    individual = []
    for group in GROUPS:
        quadra = random.choice(list(AVAILABILITY.keys()))
        horario = random.choice(AVAILABILITY[quadra])
        individual.append((group, quadra, horario))
    return individual

# Função de avaliação (fitness)
def fitness(individual):
    score = 0
    # Penaliza se duas reuniões ocorrerem no mesmo horário em uma mesma quadra
    for i, (group1, quadra1, horario1) in enumerate(individual):
        for j, (group2, quadra2, horario2) in enumerate(individual):
            if i != j and quadra1 == quadra2 and horario1 == horario2:
                score -= 1
    return score

# Função de cruzamento
def crossover(parent1, parent2):
    point = random.randint(1, len(parent1) - 1)
    child = parent1[:point] + parent2[point:]
    return child

# Função de mutação
def mutate(individual):
    if random.random() < MUTATION_RATE:
        idx = random.randint(0, len(individual) - 1)
        group, quadra, horario = individual[idx]
        new_quadra = random.choice(list(AVAILABILITY.keys()))
        new_horario = random.choice(AVAILABILITY[new_quadra])
        individual[idx] = (group, new_quadra, new_horario)

# Algoritmo Genético Principal
def genetic_algorithm():
    population = [create_individual() for _ in range(POPULATION_SIZE)]
    for generation in range(GENERATIONS):
        population = sorted(population, key=fitness, reverse=True)
        if fitness(population[0]) == 0:  # Nenhum conflito
            print(f"Solução encontrada na geração {generation}")
            return population[0]
        next_generation = population[:POPULATION_SIZE // 2]
        for i in range(POPULATION_SIZE // 2):
            parent1, parent2 = random.sample(next_generation, 2)
            child = crossover(parent1, parent2)
            mutate(child)
            next_generation.append(child)
        population = next_generation
    print("Nenhuma solução encontrada")
    return None

# Resolver o problema de agendamento
solution = genetic_algorithm()
if solution:
    for group, quadra, horario in solution:
        print(f"{group}: {quadra} às {horario}")
```
<div style="text-indent: 2em; text-align: justify;">

<h3 style="color: #070743; font-weight: bold; text-align: center;">Explicação do Algoritmo</h3>

<p>O algoritmo genético é utilizado para encontrar uma solução ótima para o problema de agendamento. Ele funciona da seguinte forma:</p>

<p><b>1. Criação Inicial:</b> A função create_individual() cria uma solução inicial aleatória, onde cada grupo é atribuído a uma quadra e horário disponíveis.

<p><b>2. Avaliação (Fitness):</b> A função fitness() calcula a qualidade de uma solução, penalizando soluções que causam conflitos, ou seja, quando mais de um grupo tenta usar a mesma quadra no mesmo horário.</p>

<p><b>3. Cruzamento:</b> O cruzamento ocorre na função crossover(), onde duas soluções "pais" são combinadas para gerar uma nova solução "filha".</p>

<p><b>4. Mutação:</b> A função mutate() faz alterações aleatórias em uma solução, trocando a quadra ou o horário de uma reunião, a fim de explorar novas soluções.</p>

<p><b>5. Iterações:</b> O algoritmo genético é executado na função genetic_algorithm(), que gera uma população inicial de soluções e aplica o processo de cruzamento e mutação por várias gerações até que uma solução válida seja encontrada.</p>
