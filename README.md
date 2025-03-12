# Resumo lab az900
Repositorio de estudos DIO para certificação AZ-900

Microsoft Azure é uma plataforma cloud completa, com recursos gratuitos e pagos para que possamos gerenciar todo nosso park de TI da empresa.
Existem recursos que estão versão prévia que temos que tomar cuidado na hora de decidir incluir eles em produção, pois a Microsoft não garante a continuidade da solução quando está com esse status.

# Benefícios nuvem
A nuvem fornece 8 benefícios que temos que levar em consideração quando for implementar em nosso trabalho
* Alta disponibilidade - Os recursos possuem um SLA de disponibilidade, onde caso algum recurso não cumpra o SLA por conta do provedor cloud temos o direito a créditos na plataforma. 
* Escalabilidade - É possível aumentar seus recursos na vertical  para poder atender as necessidades do negócio, como aumentar CPU, Storage, RAM de um servidor
* Elasticidade - Com a elasticidade podemos crescer nossos recursos na horizontal, onde através de um estudo sobre nosso nível de requisições podemos criar novos nós na infra para atender as necessidades do negócio.
* Confiabilidade - Com uma solução cloud, é possível trazer um alcance global para sua infra, ou seja, é possível ter rapidamente um ambiente com desater recovery, replicação, backups em sites diferentes, trazendo assim maior confiança para sua TI.
* Previsibilidade - É muito simples ter uma noção do seu custo e desempenho dentro dos recursos utilizados na nuvem.
* Segurança - É um item de responsabilidade hibrido, o provedor tem como responsabilidade prover recursos e ferramentas para aumentar seu nível de segurança e o cliente deve implementar tais recursos a seu ambiente de acordo com suas politicas, governança e estratégias.
* Governança - É possível gerenciar seus recursos de muitas formas diferentes, possibilitando assim atender normas, politicas externas e internas e diretrizes de segurança de acordo com cada necessidade.
* Gerenciabilidade - A gestão de seus recursos podem ser feitas pelo portal do azure, linha de comando, APIs.


A plataforma do AZURE é muito simples e intuitiva, todos os componentes criados possuem uma previsibilidade de quanto iremos ter de custo, deixando assim mais fácil mapear e gerenciar os itens que iremos criar dentro do provedor


# Componentes e arquitetura do Azure.
O Azure é dividido em regiões que estão espalhadas entre o globo.
Cada região possui suas zonas de disponibilidades que em sua maioria são 3 e as mesmas se comunicação entre si com objetivo de manter a disponibilidade dos serviços e dados, com a mínima latência.
Existem duas regiões soberanas que não são acessíveis aos usuários comuns do AZURE são elas, a do governo dos EUA e a zona da China, no caso da China existe uma operadora intermediaria chamada 21VIANET para garantir que os dados não saiam do pais.
Para organizar o Azure temos alguns recursos que facilitam são eles:
* Grupo de recursos - Agregamos um ou mais recursos de múltiplas regiões;
* Assinaturas - É utilizada quando queremos separar financeiramente nossos recursos, onde uma conta pode ter N Assinaturas porem uma assinatura só pertence a uma conta;
* Grupos de gerenciamentos - Gerencia suas assinaturas muito utilizado quando queremos criar politicas ou controles de acessos globais a diferentes assinaturas e grupo de recursos;  

# Computação no Azure
Azure trabalha com diversas soluções computação algumas PaaS outras IaaS, são elas:
* V.M. = As famosas maquinas virtuais são ofertas IaaS de maquinas windows e linux, onde o controle de maquinas são totalmente do usuário, podemos configurar conjuntos de disponibilidade, domínio de atualização, temos diversas estratégias de uso, inclusive é uma forma fácil de migrar seu ambiente on primese para cloud sem muitas alterações nas aplicações.
* Área de trabalho virtual = Uma forma de prover área de trabalho aos usuários finais da empresa de forma virtual podendo compartilhar recursos, regras e configurações de maquinas de forma simples e rápida.
* Container = Uma oferta Paas que possibilita ter um ambiente leva, escalável, sem a necessidade de gerenciar um S.O. para executar suas aplicações.
* Aplicativo de serviço = Uma oferta Paas que hospeda aplicações WEB, APIs, sem necessidade de um servidor para gerenciar o S.O. e de fácil integração com estratégia de atualização continua das aplicações, trabalha com multi linguagens.
* Azure function = Uma solução simples e leve de executar uma aplicação baseada em um evento que gere um gatilho de execução como a atualização de um arquivo, interrompimento de alguma maquina.

#Redes
  Falando sobre redes temos as Vnet que são as redes virtuais do azure, onde temos que tomar cuidado para não criar subredes dentro da mesma faixa de ip da sua rede local.
  Após isso temos a Gateway VPN = uma forma de conectar a empresa on primese com a nuvem
  Express Route = É uma conexão entre seu ambiente local com a microsoft porem com um fio.


#Armazenamento
O Azure possui diversas soluções de armazenamento para ofertar a seus usuários, todas essas opções estão contidas dentro de uma conta de armazenamento
Os serviços disponíveis são:
* Containers
* Filas
* Tabelas
* Data Lake

A retenção desses arquivos são separadas entre Quente (Dados acessados constantemente) ou Frio (Dados com baixa frequência de uso, e por isso a Microsoft cobra mais barato o arquivamento porem é mais caro o acesso).
A Redundância também está dividida em 4 opções
* LRS - Redundância local dentro do mesmo CPD
* ZRS - Redundância entre os 3 datacenter
* GPS - Redundância geográfica
* GZRS - Redundância de zona e geográfica.

# Migração 
Para migrar seus dados para o Azure, você pode fazer isso offline ou online, depende do tamanho dos dados, link utilizado entre outras informações.
Para migrar os dados temos as seguintes opções.
* Azure Data Box = dividido em 3 produtos sendo 35Tb, 80 Tb e 100 Tb, é uma copia dos dados do CPD e a mesma copia no datacenter da Microsoft.
* Az Copy = utilizado para transferir dados via internet para seu azure.

#Identidade e segurança 
A camada de segurança e identidade é essencial para manter em pleno funcionamento da cloud. Existe vários recursos para ser usado nesse sentido, onde o principal é o Azure Entra ID o antigo Azure AD. Com o Azure é possível gerenciar contas, acessos, politicas de segurança, infraestrutura. Existe soluções completas afim de deixar nosso ambiente mais seguros.

#Gerenciamento de custos
Os custos é um fator primordial para a implementação de soluções cloud darem certo em uma empresa, atualmente o maior desafio de uma equipe de administração cloud, é manter o orçamento do TI dentro das expectativas das companhias, após a pandemia muitas empresas fizeram roolback de implementações cloud que tenham feito para o on primese pelo elevado gasto mensal em manter seu ambiente, para isso o Azure possui alguns mecanismo que ajuda gerenciar bem o custo:
* Calculadora - Traz uma estimativa de custo mensal do uso de determinado serviço ou produto no Azure.
* Calculadora TCO - Gera um relatório financeiro de comparação de custo de um migração do ambiente on primese para o Azure.
* Tags - Auxiliar marcar os serviços criados no Azure para posteriormente conseguirmos visualizar na fatura exatamente onde estamos tendo maior gasto ou economia com algum produto ou serviço.

#Politicas em acessos no Azure
As polices são encessiais para manter a governança e o compliace de sua plataforma cloud. E as politicas é o meio mais eficaz de estabelecer isso, pois ela independe do nivel do usuário, ou seja, mesmo o administrator da plataforma precisa seguir o que esta determinado nas politicas.
