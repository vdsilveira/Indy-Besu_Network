
**Este repositório é baseado em uma prova de conceito (PoC) da DSR. O objetivo era provar a possibilidade de usar Indy Besu como base para Indy Ledger e mostrar como isso poderia ser feito.**


#### 🔎 [Saiba mais...](https://github.com/DSRCorporation/indy-node)

## Executando uma rede local


### Pré-requisitos

- [Docker e Docker-compose](https://docs.docker.com/compose/install/) v2 ou superior

>
⚠️ **Observação**: Se estiver no MacOS ou Windows, certifique-se de permitir que o docker use até 4G de memória na seção _Recursos_. Os sites [Docker for Mac](https://docs.docker.com/docker-for-mac/) e [Docker Desktop](https://docs.docker.com/docker-for-windows/) têm detalhes sobre como fazer isso no título "Recursos"

## Comandos

* **Inicie a rede: - execute todos os serviços dentro dos contêineres docker**
    ```bash
    ./network/scripts/run.sh
    ```

* **Pare a rede: - Pause todos os serviços dentro dos contêineres docker**
    ```bash
    ./network/scripts/stop.sh
    ```

* **Retorne a rede: - Ao executar novamente  a rede e você poderá retomar de onde parou com**
    ```bash
    ./network/scripts/resume.sh
    ```

* **Remova a rede: pare e remova todos os contêineres e imagens**
