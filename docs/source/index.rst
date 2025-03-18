Bem-vindo à documentação do aerostack2_tutorial!
================================================

**aerostack2_tutorial** é um projeto desenvolvido para os membros da equipe Ghost Drones que visa ensinar e demonstrar diversos tópicos relacionados ao uso do Aerostack2 em aplicações com drones. Este tutorial aborda desde a configuração e build com Docker até desafios avançados envolvendo tarefas com drones, treinamento de redes neurais e competições de navegação.

Desenvolvido por Lucca Gandra em 13/03/2025. Qualquer dúvida não hesite em me contatar em (luccagandra@poli.ufrj.br ou +55 22 99865-6999).

Tópicos Abordados
-----------------

1. **Build e Execução**
   - Build com Docker para ver o drone voando em simulação. OK
   - Execução com Yolo para visualizar os resultados da detecção. OK

2. **Gerenciamento de Tarefas e Arquitetura**
   - Uso do Tmux e yaml para organizar e gerenciar as tarefas. OK

3. **Desafios Práticos**
   - **Tarefa 1 - Voo e Pouso (Navegação)**: Voar, deslocar-se 2 metros para frente e pousar. OK
   - **Tarefa 2 - Waypoint Simples (Navegação)**: Voar, deslocar-se 2 metros com *facing goal*, deslocar-se 2 metros *not facing goal* e pousar. OK
   - **Tarefa 3 - Trajetória Curva (Navegação)**: Voar, realizar um círculo (curva) e pousar. OK
   - **Tarefa 4 - Slalom (Navegação)**: Dado um mundo com 3 cones, encontrar uma curva que passe por todos os pontos e pouse no landing pad final (não é necessário localizar o landing pad). OK
   - **Tarefa 5 - Marker Pose usando RGB-D (Percepção)**: Encontrar a posição de uma placa de stop utilizando uma câmera RGB-D. OK
   - **Tarefa 6 - Aruco Pose usando TF (Percepção)**: Encontrar a posição de um aruco via *tf* e visualizar com RVIZ2. OK
   - **Tarefa 7 - Bouncing Easy (Navegação, Percepção)**: Dado um mundo com vários landing pads, executar trajetórias que permitam pousar e decolar em cada landing pad (as poses dos marcadores serão fornecidas).
   - **Tarefa 8 - Treinamento com apenas um objeto (IA)**: Treinar uma rede neural convolucional para reconhecer um marcador.
   - **Tarefa 9 - Treinamento com vários objetos (IA)**: Treinar uma rede neural convolucional para reconhecer vários marcadores.

4. **Competições**
   - **Competição 1 - Drone Racing**: Dado um mundo com vários racing tracks, criar uma trajetória que passe pelo meio de todos na ordem correta.
   - **Competição 2 - Bouncing**: Em um mundo com vários landing pads:
     - Descobrir o número de marcadores.
     - Encontrar o número de landing pads utilizando uma rede treinada e pousar em cada um deles no menor tempo possível.
   - **Competição 3 – Tiro ao Alvo**: Dado um mundo com vários landing pads contendo arucos e marcadores, criar uma trajetória que permita lançar uma bolinha em cada um, mantendo uma restrição de distância dinâmica.

Instalação e Uso
----------------

Confira a seção de :doc:`usage <instalacao_e_uso>` para obter mais informações sobre a instalação e a execução do aerostack2_tutorial.

.. note::

   Este projeto está em desenvolvimento ativo e novas funcionalidades e desafios poderão ser adicionados.

.. toctree::
   :maxdepth: 2
   :caption: Conteúdo:

   build_e_execucao
   gerenciamento_de_tarefas
   desafios_praticos
   competicoes
   instalacao_e_uso