<div style="text-indent: 2em; text-align: justify;">

<h1 style="color: #070743; font-weight: bold; text-align: center">Agente baseado em lógica proposicional</h1> 

<p>
    O agente baseado em lógica proposicional utiliza proposições lógicas para inferir conhecimento sobre o ambiente e tomar decisões. Ele opera em micromundos bem definidos, como o Wumpus World, onde as regras e estados são claramente estabelecidos. Segundo Soares (2024), a lógica proposicional oferece ferramentas como a validade, a satisfatibilidade e as regras de inferência, que permitem derivar conclusões corretas e completas.
</p>

<h3 style="color: #070743; font-weight: bold; text-align: center">Processo de Inferência</h3> 
<p>
    A inferência é o núcleo da lógica proposicional, permitindo deduzir novas informações a partir de fatos e regras conhecidas. Por exemplo, no Wumpus World, o agente pode deduzir que uma célula é segura se todas as células adjacentes conhecidas não apresentam perigo, utilizando uma lógica como ¬Pit_x,y ∧ ¬Wumpus_x,y.
</p>
<p>
    Técnicas como Modus Ponens e resolução são amplamente empregadas. Modus Ponens segue a estrutura "Se P ⇒ Q e P forem verdadeiros, então Q é verdadeiro". A resolução, por outro lado, combina cláusulas complementares para deduzir novas informações. Essas abordagens garantem que o agente tome decisões com base em um modelo confiável e lógico.
</p>

<h3 style="color: #070743; font-weight: bold; text-align: center">Vantagens e Limitações</h3> 
<p>
    <strong>Eficiência em Ambientes Controlados:</strong> Agentes lógicos são ideais para resolver problemas em micromundos bem definidos, como jogos e simulações. O Wumpus World é um exemplo clássico usado para ilustrar a inferência em IA (RUSSELL; NORVIG, 2021).
</p>
<p>
    <strong>Limitações Práticas:</strong> A lógica proposicional carece de expressividade para lidar com incertezas ou relações complexas. Em ambientes reais, isso pode limitar a aplicação prática, como observado por Levesque e Lakemeyer (2001).
</p>

<h3 style="color: #070743; font-weight: bold; text-align: center">Impacto na Inteligência Artificial Moderna</h3> 
<p>
    Apesar de suas limitações, agentes baseados em lógica proposicional estabeleceram fundamentos importantes para a IA, como o raciocínio simbólico e o planejamento. Esses conceitos são usados em sistemas de verificação formal e automação de provas matemáticas.
</p>
<p>
    Um exemplo de aplicação prática é a automação de diagnósticos médicos. Por exemplo, regras como "Se febre ∧ tosse ⇒ gripe" podem ser usadas em sistemas especialistas para sugerir diagnósticos baseados em sintomas.
</p>

<h3 style="color: #070743; font-weight: bold; text-align: center">Exemplo Prático</h3> 

<p>Aqui está um exemplo prático de um agente baseado em lógica proposicional que simula a tomada de decisão de um ciclista ao pedalar por um caminho cheio de possíveis obstáculos. O agente é projetado para perceber o ambiente, identificar o tipo de obstáculo (como crianças atravessando, lixo na pista ou buracos no chão) e tomar a ação apropriada com base em regras predefinidas. Essas regras representam a base de conhecimento do agente, permitindo que ele associe percepções a ações específicas e reaja de forma lógica e eficiente.

</div>

```python
class BicycleAgent:
    def __init__(self):
        # Base de conhecimento (regras de lógica proposicional)
        self.knowledge_base = {
            "obstacle_child": "stop",
            "obstacle_trash": "swerve_right",
            "obstacle_hole": "swerve_left",
            "no_obstacle": "move_forward"
        }

    def perceive_environment(self, perception):
        """
        Simula a percepção do ambiente e retorna a proposição correspondente.
        """
        if perception == "child":
            return "obstacle_child"
        elif perception == "trash":
            return "obstacle_trash"
        elif perception == "hole":
            return "obstacle_hole"
        else:
            return "no_obstacle"

    def decide_action(self, proposition):
        """
        Toma uma decisão com base na base de conhecimento e na proposição percebida.
        """
        return self.knowledge_base.get(proposition, "wait")

    def act(self, perception):
        """
        Fluxo completo: percepção -> decisão -> ação.
        """
        proposition = self.perceive_environment(perception)
        action = self.decide_action(proposition)
        print(f"Perception: {perception}")
        print(f"Proposition: {proposition}")
        print(f"Action: {action}\n")


# Simulação do ambiente
def simulate_bicycle_agent():
    agent = BicycleAgent()

    # Lista de percepções simulando obstáculos no caminho
    perceptions = ["child", "trash", "hole", "no_obstacle", "trash", "child"]

    for perception in perceptions:
        agent.act(perception)


if __name__ == "__main__":
    simulate_bicycle_agent()
```
<div style="text-indent: 2em; text-align: justify;">
<h4 style="color: #070743; font-weight: bold;">Explicação do Algoritmo</h4>

<p><b>1. Base de Conhecimento:</b> É definida como um dicionário onde cada proposição é mapeada para uma ação específica.

<p><b>2. Percepção:</b> O método perceive_environment traduz as percepções (crianças, lixo, buracos, etc.) em proposições.

<p><b>3. Decisão:</b> O método decide_action utiliza a base de conhecimento para determinar a ação apropriada com base na proposição recebida.

<p><b>4. Ação:</b>O método act integra os passos de percepção, decisão e execução da ação, exibindo o fluxo completo para cada percepção.

<p><b>4. Simulação:</b>A função simulate_bicycle_agent cria uma instância do agente e processa uma sequência de percepções, representando diferentes obstáculos encontrados no caminho.

<h4 style="color: #070743; font-weight: bold;">Saída do Algoritmo</h4>
</div>

```python
Perception: child
Proposition: obstacle_child
Action: stop

Perception: trash
Proposition: obstacle_trash
Action: swerve_right

Perception: hole
Proposition: obstacle_hole
Action: swerve_left

Perception: no_obstacle
Proposition: no_obstacle
Action: move_forward

Perception: trash
Proposition: obstacle_trash
Action: swerve_right

Perception: child
Proposition: obstacle_child
Action: stop
```
Esse exemplo mostra como o agente decide ações baseadas em percepções do ambiente utilizando lógica proposicional.

<div style="text-indent: 2em; text-align: justify;">
<h3 style="color: #070743; font-weight: bold; text-align: center">Conclusão</h3> 
<p>
    Agentes baseados em lógica proposicional são ferramentas poderosas em ambientes controlados, mas possuem limitações práticas em cenários complexos. No entanto, eles continuam sendo uma base teórica essencial para avanços em inteligência artificial.
</p>
