# Visão Geral do Armazenamento e Migração no Microsoft Azure

## Projeto Armazenamento no Azure - Bootcamp AZ900

O ecossistema de armazenamento da Microsoft Azure, oferece uma plataforma robusta, escalável e segura para uma vasta gama de necessidades de dados.

## A Base: Conta de Armazenamento (Storage Account)

O ponto de partida para qualquer estratégia de armazenamento é a **Conta de Armazenamento (Storage Account)**, que funciona como um namespace único e um contêiner administrativo para todos os seus objetos de dados no Azure. Ao criar uma conta de armazenamento, você define configurações fundamentais que impactarão o desempenho, o custo e, crucialmente, a durabilidade dos seus dados. Uma das decisões mais importantes nesse momento é a escolha da **redundância**, que determina como e onde seus dados são replicados para proteção contra falhas de hardware ou desastres em larga escala.

## Estratégias de Redundância

As opções de redundância são projetadas para diferentes níveis de resiliência:

* **LRS (Locally-Redundant Storage):** A opção mais básica, que mantém três cópias síncronas dos seus dados dentro de um único datacenter. É a de menor custo, protegendo contra falhas de disco ou rack, mas vulnerável a um desastre no datacenter.
* **ZRS (Zone-Redundant Storage):** Replica seus dados sincronicamente entre três Zonas de Disponibilidade (datacenters fisicamente separados) dentro de uma única região, oferecendo proteção contra a falha de um datacenter inteiro.
* **GRS (Geo-Redundant Storage):** Copia seus dados de forma síncrona três vezes na região primária (como o LRS) e, em seguida, replica esses dados de forma assíncrona para uma região secundária a centenas de quilômetros de distância, protegendo contra desastres regionais.
* **GZRS (Geo-Zone-Redundant Storage):** A opção mais resiliente, que combina o melhor dos dois mundos: replica os dados entre as Zonas de Disponibilidade na região primária (como o ZRS) e também os copia de forma assíncrona para uma região secundária.

## Tipos de Serviços de Dados

Dentro de uma conta de armazenamento, o Azure disponibiliza quatro tipos primários de serviços de dados:

* **Armazenamento de Blobs (Containers):** O serviço mais comum, projetado para armazenar enormes quantidades de dados não estruturados, como imagens, vídeos, arquivos de log, backups e documentos. Os dados são organizados em "contêineres" e os arquivos são chamados de "blobs".

* **Compartilhamento de Arquivos (Azure Files):** Oferece compartilhamentos de arquivos totalmente gerenciados na nuvem, acessíveis através dos protocolos padrão **SMB (Server Message Block)** e **NFS (Network File System)**. A autenticação pode ser feita com a chave da conta ou, de forma mais segura, via integração com o Azure Active Directory para autenticação baseada em identidade (Kerberos).

* **Armazenamento de Filas (Queues):** Fornece uma plataforma de mensagens simples e confiável para desacoplar componentes de aplicações, permitindo que processos se comuniquem de forma assíncrona.

* **Armazenamento de Tabelas (Tables):** Um serviço NoSQL que armazena grandes volumes de dados estruturados não relacionais (chave-valor) com um esquema flexível. A segurança de acesso é controlada através de **Políticas de Acesso e Assinaturas de Acesso Compartilhado (SAS - Shared Access Signatures)**, que concedem permissões delegadas e temporárias a recursos específicos.

## Migração para o Azure

Quando uma organização decide mover suas operações para a nuvem, o **Azure Migrate** funciona como um hub unificado para descobrir, avaliar e migrar cargas de trabalho on-premises.

* **Migração de Servidores:** O Azure Migrate utiliza uma ferramenta para descobrir VMs e servidores físicos, avaliar a compatibilidade e orquestrar a replicação para o Azure usando a tecnologia do **Azure Site Recovery**, minimizando o tempo de inatividade.

* **Migração de Bancos de Dados:** O **Serviço de Migração de Banco de Dados (DMS)** simplifica a movimentação de bancos de dados (SQL Server, MySQL, etc.) para as ofertas de PaaS do Azure, como o Banco de Dados SQL do Azure ou a Instância Gerenciada SQL.

* **Migração de Aplicativos Web:** A ferramenta **Azure App Service Migration Assistant** analisa aplicações web em execução no IIS (Internet Information Services) e automatiza o processo de movê-las para o Azure App Service.

## Ferramenta de Transferência: AzCopy

Para a tarefa prática de mover grandes volumes de arquivos de e para as contas de armazenamento do Azure, existe a ferramenta de linha de comando **AzCopy**. É um utilitário de alta performance otimizado para a transferência de dados em massa, permitindo copiar blobs ou arquivos de forma rápida, confiável e automatizada.

## Conclusão

Em conjunto, essas soluções formam um ecossistema completo que permite não apenas armazenar dados de forma segura e resiliente, mas também gerenciar, acessar e migrar cargas de trabalho complexas para a nuvem da Microsoft de maneira estruturada e eficiente.
