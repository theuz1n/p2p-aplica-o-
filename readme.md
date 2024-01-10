
Uma aplicação p2p é um sistema distribuído de compartilhamento de arquivos com duas entidades principais:

## Tracker

- Atua como um servidor central, servindo como uma ponte entre os clientes.
- Não armazena arquivos, registros de buscas ou histórico de clientes.

## Cliente

- Baixa e/ou compartilha arquivos.
- Fornece uma interface para o usuário do sistema.
- Opera em dois modos:
    - **Cliente Solicitante (leecher):** Baixa arquivos.
    - **Cliente Compartilhante (seeder):** Fornece arquivos.
- Um mesmo Cliente pode atuar simultaneamente como leecher e seeder, realizando tanto o download quanto o compartilhamento de arquivos.

#   p2p aplicação - Passos para Download

Em resumo, os passos para um Cliente baixar um arquivo no p2p são os seguintes:

1. O usuário abre um Cliente, que atua como Cliente Solicitante (leecher), escolhe a opção de busca de arquivo e digita o nome do arquivo desejado.

2. O Cliente Solicitante (leecher) envia a busca para o Tracker.

3. O Tracker repassa a busca para todos os outros Clientes conectados a ele.

4. Os Clientes recebem a consulta, verificam se possuem o arquivo e respondem ao Tracker com informações do arquivo se o tiverem, tornando-se Clientes Compartilhantes (seeder). Os Clientes sem o arquivo respondem com uma mensagem negativa.

5. O Tracker compila as respostas em uma lista, adiciona os IPs dos Clientes Compartilhantes (seeder) e envia a resposta para o Cliente Solicitante (leecher).

6. O Cliente Solicitante (leecher), com a lista em mãos, contata os Clientes Compartilhantes (seeder) para iniciar o download do arquivo.

## Cliente

O Cliente PyShare é projetado para permitir o compartilhamento de arquivos de forma eficiente em uma rede peer-to-peer (P2P). Aqui estão as principais características do Cliente:

### Estrutura de Diretórios

- O Cliente possui um diretório chamado "Download" dedicado ao armazenamento de arquivos baixados e disponíveis para compartilhamento.
- Os arquivos em processo de download são temporariamente armazenados no diretório "Temp".

### Seeder e Leecher

- O Cliente atua simultaneamente como seeder e leecher.
- Quando atua como seeder, serve através de uma porta específica (fixa ou aleatória entre 60000 e 61000) para atender às requisições dos leechers e do Tracker.

### Menu Principal

- Apresenta um menu interativo na thread principal, com opções como:
    - (1) Baixar Arquivo
    - (2) Listar Arquivos (pasta Download)
    - (3) Sair

### Restrições de Download

- O Cliente (leecher) é limitado a baixar apenas um arquivo por vez.
- Durante o download, a interface permanece ocupada até a conclusão do processo.
- O Cliente (seeder) é capaz de servir vários arquivos simultaneamente para outros Clientes.

## Servidor

O Servidor PyShare age como uma ponte eficiente entre leechers e seeders na rede P2P. Suas principais funcionalidades incluem:

### Armazenamento

- Não mantém armazenamento de arquivos, registros de buscas ou histórico de clientes.

### Conectividade

- Mantém uma lista atualizada dos clientes conectados na rede.

### Multiconexão

- Capacidade de atender múltiplos clientes simultaneamente.

### Única Função

- A única função do servidor é facilitar a comunicação entre leechers e seeders, garantindo uma troca eficiente de arquivos na rede P2P.

## Execução

1. **Cliente:**
    
    - Execute o cliente para iniciar a interação e compartilhamento de arquivos.
    - Utilize o menu para baixar, listar arquivos ou sair.
2. **Servidor:**
    
    - Inicie o servidor para facilitar a comunicação entre os clientes.
    - O servidor trabalha nos bastidores, conectando leechers e seeders na rede.

## Observações

- Certifique-se de configurar as portas adequadamente para permitir a comunicação eficiente entre os clientes e o servidor.
- Respeite as leis locais e regulamentos ao compartilhar arquivos na rede P2P.

Divirta-se compartilhando e baixando arquivos com o PyShare!