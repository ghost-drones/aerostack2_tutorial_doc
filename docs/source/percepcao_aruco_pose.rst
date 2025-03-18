Tarefa 6 - Aruco Pose usando TF (Percepção)
===========================================

Esta página pertence ao tópico de percepção, demonstrando como encontrar a posição de um aruco utilizando TF e visualizar com RVIZ. O seu drone não deve sair do solo. 

Mundo: "empty" com esse objeto estático

```
objects:
  - model_name: "aruco_gate"
    model_type: "aruco_gate_1"
    xyz:
      - 4.0
      - 1.3
      - 0.0
    rpy:
      - 0.0
      - 0.0
      - 3.14159
```