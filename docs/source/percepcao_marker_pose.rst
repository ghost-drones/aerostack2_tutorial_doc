Tarefa 5 - Marker Pose usando RGB-D (Percepção)
===============================================

Esta página pertence ao tópico de percepção, demonstrando como encontrar a posição de uma placa de stop utilizando uma câmera RGB-D. O seu drone não deve sair do solo.

Utilize os exemplos presentes em https://github.com/mgonzs13/yolo_ros como inspiração para seu trabalho.

Obs: configuração de pacotes e debug é a parte mais chata de um trabalho com ROS2 e Ubuntu. Não desista... o pacote está configurado corretamente, basta aprender a configurar.

Mundo: "empty" com esse objeto estático

```
objects:
  - model_name: "hexagono_vermelho"
    model_type: "hexagono_vermelho_fixed"
    xyz:
      - 5.0
      - 2.0
      - 1.35
    rpy:
      - 0.0
      - -1.5707
      - 0.0
```