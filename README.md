## Introdução
 O Hyperledger Indy  é um framework de código com foco em criaçao sistemas de identidade descentralizadas e auto-soberanas.

O Hyperledger Besu é uma implementação de código aberto da Ethereum Virtual Machine (EVM) desenvolvida pelo ConsenSys.O Besu é projetado para ser altamente modular e flexível, permitindo que organizações construam redes de blockchain privadas, públicas ou híbridas. Ele suporta a execução de contratos inteligentes e a interoperabilidade com redes Ethereum.

Este  repositório faz parte de uma prova de conceito (PoC) que tem por objetivo  oferecer a possibilidade de uso do Hyperledger Besu como base para uma Ledger Indy  na criação  de identidade descentralizadas, mais especificamente, a parte de estabelecimento da rede Besu. 

## Executando rede local


### Pré-requisitos

- [Docker e Docker-compose](https://docs.docker.com/compose/install/) v2 ou superior
  
- [Carteira Metamask ](https://metamask.io/) 

  
⚠️ **Observação**: Se estiver no MacOS ou Windows, certifique-se de permitir que o docker use até 4G de memória na seção _Recursos_. Os sites [Docker for Mac](https://docs.docker.com/docker-for-mac/) e [Docker Desktop](https://docs.docker.com/docker-for-windows/) têm detalhes sobre como fazer isso no título "Recursos"

## Comandos

* **Clone o repositório: - copie as pastas para sua máquina**
    ```bash
    git clone https://github.com/vdsilveira/Indy-Besu_For_DIDs-Anoncreds.git


    ```

* **Inicie a rede: - execute todos os serviços dentro dos contêineres Docker**
    ```bash
    ./network/scripts/run.sh
    ```

* **Pare a rede: - Pause todos os serviços dentro dos contêineres Docker**
    ```bash
    ./network/scripts/stop.sh
    ```

* **Retorne a rede: - Ao executar novamente a rede, você poderá retomar de onde parou**
    ```bash
    ./network/scripts/resume.sh
    ```

* **Remova a rede: pare e remova todos os contêineres e imagens**
    ```bash
    ./network/scripts/remove.sh
    ```

## 📄 Inicializando contratos Inteligentes 
 
  ### Metamask
O MetaMask é uma carteira de criptomoedas e uma extensão de navegador que permite aos usuários acessar a blockchain Ethereum e interagir com aplicativos descentralizados (dApps). Ele facilita o gerenciamento de chaves privadas, armazenamento e envio de tokens Ethereum, além de possibilitar a interação com contratos inteligentes. Atuando como uma ponte entre o navegador e a blockchain Ethereum, o MetaMask torna mais fácil para os usuários acessarem dApps diretamente de seus navegadores, sem a necessidade de executar um nó Ethereum completo, o que amplia a acessibilidade e o uso dos aplicativos descentralizados.

  #### Configurando Metamask

  Em adicionar rede, configure sua Metamask com seu endereço de IP e porta 8545 no campo "New RPC URL" e 1337 em "Chain ID".

  
   `OBS: as configurações de Porta e Chain Id podem ser alteradas no genesis.json [.network/config/besu/genesis.json]`


<img src="./img/CCaptura de tela de 2024-02-19 12-40-32.png">

  ### IDE Remix

  A  Remix é uma ferramenta de desenvolvimento integrado (IDE, na sigla em inglês) usada para escrever, testar e implantar contratos inteligentes na blockchain Ethereum. Ela é amplamente utilizada por desenvolvedores de contratos inteligentes devido à sua interface amigável e recursos robustos.

Para interação com os contratos inteligentes [abra a IDE remix](https://remix.ethereum.org/)

#### Interagindo com os contratos:

* #### Faça o upload da pasta contracts do repositório para a IDE:
   
   `../indy-besu/smart_contracts/contracts`
  
  <img src="./img/Captura de tela de 2024-02-08 08-33-58.png">

* #### Selecione os contratos:
  <img src="./img/Captura de tela de 2024-02-08 10-59-44.png">


- #### Compile o contrato na IDE Remix:
  <img src="./img/Captura de tela de 2024-02-08 08-38-35.png">

- #### No arquivo genesis.json você   encontrará  o endereço do contrato:

    
   `../indy-besu/network/config/besu`
 
  <img src="./img/Captura de tela de 2024-02-08 08-44-37.png">
  
     #### Lista de endereço dos contratos:


   * `contracts/auth/`  AccountControl.sol - `0xaf926ec0acfe1ea2df5da1154ff901ffe158cc77`
   * `contracts/auth/`RoleControl.sol - `0xade94cfdeae7a82237f83a3bc41fbc940def1db7`
   * `contracts/cl/`CredentialDefinitionRegistry.sol - `0xab1d436a6f97f7a0b08ceb700dae0903ee6f314b`
   * `contracts/cl/`SchemaRegistry.sol -`0x6073e9c8702975dcbe1736e0921ce748f99bd20e`
   * `contracts/did/`IndyDidRegistry.sol -`0x4def1dfa07d1c68b0282f323b268e9d26418e776`
   * `contracts/did/`UniversalDidResolver.sol -`0x3522f71f8c3cd8a3f7e66ce2806594b0914247da`
   * `contracts/did/`EthereumExtDidRegistry.sol -`0x3208a66afef77854a62da174944247049778d9b6`
   * `contracts/upgrade`UpgradeControl.sol -`0x431b0ec220a7f17b7c89ddd7375f36929332d3c8`

  
- #### Chame os contratos inteligentes:
  <img src="./img/Captura de tela de 2024-02-08 08-46-25.png">


- #### Inicializando os contratos
   `OBS: É necessario a inicialização de todos so contratos antes de conseguir utilizar as funções`

  <img src="./img/Captura de tela de 2024-02-08 09-00-04.png">




##  🔗 Interagindo com os  contratos Inteligentes 

   `OBS: Utilize as tuplas a seguir para interagir com os contratos na ordem especificada`
#### 1 - Create DID:


 `[[],"did:indy2:testnet:SEp33q43PsdP7nDATyySSH",[],[["did:indy2:testnet:SEp33q43PsdP7nDATyySSH#KEY-1","Ed25519VerificationKey2018","did:indy2:testnet:N22SEp33q43PsdP7nDATyySSH""zAKJP3f7BD6W4iWEQ9jwndVTCBq8ua2Utt8EEjJ6Vxsf",""]],[\["did:indy2:testnet:SEp33q43PsdP7nDATyySSH#KEY-1",["","","","",""]]],[],[],[],[],[],[]]`


#### 2 - Create Schema:

`["did:indy2:testnet:SEp33q43PsdP7nDATyySSH/anoncreds/v0/SCHEMA/BasicIdentity/1.0.0","did:indy2:testnet:SEp33q43PsdP7nDATyySSH", "BasicIdentity","1.0.0", ["First Name","Last Name"]]`

#### 3 - Create Credential Definition:

`["did:indy2:testnet:SEp33q43PsdP7nDATyySSH/anoncreds/v0/CLAIM_DEF/did:indy2:testnet:SEp33q43PsdP7nDATyySSH/anoncreds/v0/SCHEMA/BasicIdentity/1.0.0/BasicIdentity","did:indy2:testnet:SEp33q43PsdP7nDATyySSH","did:indy2:testnet:SEp33q43PsdP7nDATyySSH/anoncreds/v0/SCHEMA/BasicIdentity/1.0.0","CL","BasicIdentity","<keys>"]`







