Tarefa 7 - Treinamento com vários objetos (IA)
===============================================

Objetivo: Treinar uma rede neural com objetos customizados e visualizar o resultado no Gazebo. 
Você deverá criar uma rede para identificar todos os 7 marcadores da competição Eletroquad.

.. note::

    Utilize o vídeo `Train YOLO Object in Google Colab <https://www.youtube.com/watch?v=r0RspiLG260>`_ como inspiração para seu trabalho. Você não precisa criar arquivos
    .py para resolver o problema. Seja criativo e utilize técnicas criativas para gerar mais fotos do mesmo marcador (ângulos diferentes, iluminações, etc).

Ao final da tarefa, você deve inserir o modelo .pt treinado na pasta do yolo_ros e executar a simulação
com Yolo e os marcadores para verificar o resultado.

Use a configuração 3 de mundo eletroquad:

.. code-block:: bash

   . launch_eletroquad_as2.bash -3

Lembre-se de que o modelo treinado será executado em uma Raspberry Pi 4,
que possui capacidade de processamento inferior à do seu computador. 
Portanto, opte por uma arquitetura de rede "tiny". Além disso, verifique a taxa de atualização 
do tópico de inferência da rede. Se essa taxa estiver baixa, isso indica que a inferência do modelo 
está lenta, e provavelmente será até cinco vezes mais lenta na Raspberry Pi.

Comando para verificar taxa de atualização de um tópico no ROS2:

.. code-block:: bash

   ros2 topic hz /nome_do_topico

Comportamento esperado: