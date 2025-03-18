Tarefa 7 - Bouncing Easy (Navegação, Percepção)
===============================================

Esta página pertence ao tópico de navegação e percepção, demonstrando como executar trajetórias que permitam pousar e decolar em cada landing pad.

Utilize os exemplos presentes em `/examples` como inspiração para seu trabalho.

Mundo: "empty" com esses objetos estáticos.

Obs: as poses de cada marcador estão sendo publicadas em tópicos ROS2. Use esses tópicos para achar a pose de cada um e calcular a rota.

```
objects:
  - model_name: "marker_1"
    model_type: "circulo_azul"
    object_bridges:
      - "pose"
    xyz:
      - 0.7
      - 0.0
      - 0.01
  - model_name: "marker_2"
    model_type: "cruz_rosa"
    object_bridges:
      - "pose"
    xyz:
      - -1.38
      - 1.15
      - 0.01
  - model_name: "marker_3"
    model_type: "estrela_verde"
    object_bridges:
      - "pose"
    xyz:
      - 2.19
      - -1.72
      - 0.01
  - model_name: "marker_4"
    model_type: "hexagono_vermelho"
    object_bridges:
      - "pose"
    xyz:
      - 2.88
      - -0.2
      - 0.01
  - model_name: "marker_5"
    model_type: "pentagono_marrom"
    object_bridges:
      - "pose"
    xyz:
      - -1.6
      - -0.9
      - 0.01
  - model_name: "marker_6"
    model_type: "triangulo_azul"
    object_bridges:
      - "pose"
    xyz:
      - 1.0
      - -1.6
      - 0.01
```