Execução com Yolo
=================

Esta página pertence ao tópico "execução com yolo para visualizar os resultados da detecção".

Conteúdo básico: Aqui você aprenderá como executar o Yolo e analisar os resultados.

---

Execução dentro do Docker
=========================

Assim que estiver dentro do Docker, vá até a pasta do `aerostack2_tutorial`:

```bash
cd /root/tutorials/src/aerostack2_tutorial
```

Para executar a simulação, utilize um dos seguintes comandos:

```bash
. launch_as2.bash  # Simulação padrão
. launch_yolo_as2.bash  # Simulação com YOLO
```

### Diferença entre os arquivos de lançamento

A única diferença entre `launch_as2.bash` e `launch_yolo_as2.bash` está no arquivo `.yaml` que define as configurações da simulação. Para modificar qualquer parâmetro da simulação com YOLO, edite o arquivo yaml que corresponde à sua simulação. Eles estão presentes em:

```
/tmuxinator
```

Nesse arquivo, você pode:
- Adicionar ou remover abas no TMUX
- Modificar condições de execução
- Ajustar parâmetros da simulação

### Configuração da YOLO

Para executar a YOLO na simulação, altere os parâmetros no arquivo `aerostack2_yolo.yaml`. Aqui está um exemplo de comando para iniciar a YOLO na minha máquina com GPU Nvidia:

```bash
ros2 launch yolo_bringup yolov8.launch.py use_3d:=False input_image_topic:=/drone0/sensor_measurements/gimbal/camera/image_raw device:=cuda:0
```

Caso você **não tenha uma GPU Nvidia** ou **não tenha configurado o container com o NVIDIA Container Toolkit**, use a CPU:

```bash
device:=cpu
```

Além disso, você deve alterar o mundo em `config/world.yaml` para `yolo_test`.

Para visualizar a imagem gerada pela rede neural, basta abrir o rviz2 (`rviz2` no terminal) e selecionar o tópico de imagem gerado pelo wrapper da Yolo.

Obs: crie uma nova aba do Docker Container (docker exec -it aerostack2_humble_cont /bin/bash) ou crie nova janela/aba pelo arquivo de configuração tmuxinator.