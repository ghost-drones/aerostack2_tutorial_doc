Tarefa 4 - Slalom (Navegação)
=============================

Esta página pertence ao tópico de navegação, demonstrando a tarefa de encontrar uma curva que passe por 5 cones e pousar no landing pad final. O seu drone não deve ultrapassar a altitude de 2.5 metros (altura dos cones).
Além disso, o drone deve passar pelos cones pelas direções, em ordem:

- Esquerda
- Direita
- Esquerda
- Esquerda
- Direita

Utilize os exemplos presentes em `/examples` como inspiração para seu trabalho.

Mundo: "empty" com esses objetos estáticos:

```
objects:
  - model_name: "base_inicial"
    model_type: "circulo_azul"
    xyz:
      - 0.0
      - 0.0
      - 0.01
  - model_name: "barra_1"
    model_type: "barra_azul"
    xyz:
      - 2.0
      - 0.0
      - 0.0
  - model_name: "barra_2"
    model_type: "barra_preto_fosco"
    xyz:
      - 4.0
      - -1.2
      - 0.0
  - model_name: "barra_3"
    model_type: "barra_azul"
    xyz:
      - 6.0
      - 1.1
      - 0.0
  - model_name: "barra_4"
    model_type: "barra_rosa"
    xyz:
      - 8.0
      - 2.7
      - 0.0
  - model_name: "barra_5"
    model_type: "barra_vermelha"
    xyz:
      - 10.0
      - -0.1
      - 0.0
  - model_name: "base_final"
    model_type: "cruz_rosa"
    xyz:
      - 12.0
      - -3.0
      - 0.01
```
Comportamento esperado:
