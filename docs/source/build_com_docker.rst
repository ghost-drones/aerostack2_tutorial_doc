Build com Docker
================

Esta página pertence ao tópico "build com docker para ver o drone voando em simulação".

Conteúdo básico: Aqui você aprenderá como configurar e realizar o build do ambiente Docker.

Instalação do Docker Engine
---------------------------

Siga os passos abaixo para instalar o Docker Engine no Ubuntu. Fonte: https://docs.docker.com/engine/install/ubuntu/

1. Adicione a chave GPG oficial do Docker:

   ```bash
   sudo apt-get update
   sudo apt-get install ca-certificates curl
   sudo install -m 0755 -d /etc/apt/keyrings
   sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
   sudo chmod a+r /etc/apt/keyrings/docker.asc
   ```

2. Configure o repositório oficial do Docker:

   ```bash
   echo \  
     "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \  
     $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \  
     sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   sudo apt-get update
   ```

3. Instale os pacotes do Docker:

   ```bash
   sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   ```

Executando Docker sem sudo
--------------------------

Após a instalação, configure o Docker para ser executado sem `sudo`.

1. Crie o grupo `docker` e adicione seu usuário:

   ```bash
   sudo groupadd docker
   sudo usermod -aG docker $USER
   sudo reboot
   ```

2. Após reiniciar, execute:

   ```bash
   newgrp docker
   ```

Instalação do NVIDIA Container Toolkit (Opcional)
-------------------------------------------------

Se você possui uma GPU da NVIDIA, siga esses passos para configurar o suporte ao Docker. Fonte: https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html

1. Configure o repositório de produção:

   ```bash
   curl -fsSL https://nvidia.github.io/libnvidia-container/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg && \
   curl -s -L https://nvidia.github.io/libnvidia-container/stable/deb/nvidia-container-toolkit.list | \
     sed 's#deb https://#deb [signed-by=/usr/share/keyrings/nvidia-container-toolkit-keyring.gpg] https://#g' | \
     sudo tee /etc/apt/sources.list.d/nvidia-container-toolkit.list
   ```

2. Opcionalmente, ative pacotes experimentais:

   ```bash
   sed -i -e '/experimental/ s/^#//g' /etc/apt/sources.list.d/nvidia-container-toolkit.list
   ```

3. Atualize os pacotes e instale o NVIDIA Container Toolkit:

   ```bash
   sudo apt-get update
   sudo apt-get install -y nvidia-container-toolkit
   ```

4. Configure o Docker para utilizar a NVIDIA Container Runtime:

   ```bash
   sudo nvidia-ctk runtime configure --runtime=docker
   ```

5. Reinicie o daemon do Docker:

   ```bash
   sudo systemctl restart docker
   ```

Habilitando Aplicações Gráficas no Container
--------------------------------------------

Para permitir a execução de aplicações gráficas dentro do container, execute:

```bash
xhost +local:docker
```

Para evitar a necessidade de rodar esse comando sempre, adicione-o ao seu `.profile`:

```bash
echo "xhost +local:docker > /dev/null" >> ~/.profile
```

Build e Execução do Container Docker
-------------------------------------

Siga os passos abaixo para criar e executar um container Docker com o Aerostack2.

1. Clone o repositório do projeto:

   ```bash
   git clone git@github.com:ghost-drones/aerostack2_tutorial.git
   ```

2. Configure a variável de ambiente para ativar o BuildKit:

   ```bash
   export DOCKER_BUILDKIT=1
   ```

3. Compile a imagem do Docker a partir do diretório raiz do projeto:

   ```bash
   docker build --ssh default -t aerostack2_humble_img .
   ```

4. Execute o container pela primeira vez:

   ```bash
   ./first_run.sh
   ```

   Esse script criará um container chamado `aerostack2_humble_cont` e abrirá um terminal dentro dele.

5. Para reutilizar o container em sessões futuras, utilize:

   ```bash
   docker start -i aerostack2_humble_cont
   ```

Outros Comandos Úteis
---------------------

- Para abrir outro shell dentro do container em execução:

  ```bash
  docker exec -it aerostack2_humble_cont bash
  ```

- Para parar o container:

  ```bash
  docker stop aerostack2_humble_cont
  ```

- Para remover o container:

  ```bash
  docker rm aerostack2_humble_cont
  ```

Se o container for removido, você sempre pode recriá-lo do zero executando o script `first_run.sh` novamente.

---

Com essa configuração, seu ambiente estará pronto para rodar simulações do Aerostack2 utilizando Docker.