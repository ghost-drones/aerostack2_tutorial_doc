Tarefa 5 - Aruco Pose usando TF (Percepção)
===========================================

Objetivo: encontrar a posição de um aruco utilizando TF e visualizar com RVIZ. O seu drone não deve sair do solo. 

.. note::

  Utilize os exemplos presentes em `/examples` como inspiração para seu trabalho. 
  Nomeie o arquivo como `mission_aruco_pose.py`.

  `Detect ArUco Markers Behavior <https://aerostack2.github.io/_04_robot_behaviors/index.html>`_ para resolver essa tarefa. Lembre-se que os parâmetros intrínsecos
  da câmera sempre são publicado em tópicos do tipo CameraInfo.

Mundo: "empty" com esse objeto estático

.. code-block:: yaml

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