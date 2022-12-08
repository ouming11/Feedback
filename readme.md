(Informações Técnicas Open Finance)[https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17371213/Informa+es+T+cnicas+-+Cart+o+de+Cr+dito+-+v2.0.1]
(ISO 20022)[https://www.iso20022.org/iso-20022-message-definitions?business-domain=16]
(ISO 8583)[https://en.wikipedia.org/wiki/ISO_8583]
(Serviços necessários Cartões e Parceiro)[https://paranabancoprod-my.sharepoint.com/:w:/g/personal/arthurfs_paranabanco_com_br/ETqq1ze6xi5CsI-IFgp5VZ0Bd0UqsflDfx-XW3VhkGEIiQ?e=ftNzri&wdOrigin=TEAMS-ELECTRON.p2p.bim&wdExp=TEAMS-CONTROL&wdhostclicktime=1668433877400&web=1]

## Swashbuckle
(Referência Swashbucle)[https://learn.microsoft.com/en-us/aspnet/core/tutorials/getting-started-with-swashbuckle?view=aspnetcore-6.0&tabs=visual-studio-mac#xml-comments]
No `Startup.cs`, `ConfigureServices` é preciso adicionar também a carga do XML de documentação do projeto adicionado como referência, que contém as models:
``` csharp
c.IncludeXmlComments(modelXmlPath);
```
E para que as propriedades sejam corretamente renderizadas para os tipos `enum` é preciso também adicionar um `SchemaFilter` customizado:
``` csharp
c.SchemaFilter<EnumTypeLowerCamelCaseSchemaFilter>(modelXmlPath);
```



## PrbCartao
### Escopo do sistema e seus objetivos
Substituir o MVP PrbCartaoBeneficio, oferecendo ao cliente PB a possibilidade de contratar um Cartão, independentemente de tipo (crédito, débito, voucher, frota, combo), canal, convênio, bandeira ou processadora.
Deve seguir as especificações de mercado, permitindo evolução contínua e integrações com diversos parceiros e sistemas, levando em consideração:
- ISO 20022
- ISO 8583
- Open Finance
- Normativas dos órgãos envolvidos

Deve, principalmente, estar integrado com os demais serviços corporativos existentes no PB, como PrbPessoa, PrbDadosBancarios, PrbOfertaUnica, PrbOportunidade etc.

### Qual é a finalidade do sistema e quais funcionalidades ele deve ter?
APIs e serviços que permitam:
- Emissão / reemissão de cartões
- Cancelamento (via sistema) e estorno (via solicitação) de operações
- Ativação e desativação de funcionalidades
- Criação e troca de senha
- Bloqueio e desbloqueio
- Saque, Saque Complementar, Compra, ajuste de limites
- Pagamento de faturas
- Liquidação de dívidas
- Parcelamento de dívidas
- Contestação de lançamentos indevidos
- Pesquisa de situação, saldos, limites, faturas, dívidas, parcelamentos, tanto para o cliente quanto para Atendimento
- Atender a clientes existentes e inéditos
- Emissão de documentos, arquivos etc, para atender requisitos de contabilidade, legais e de conformidade

### A fazer    
- Realize uma análise de requisitos para identificar as necessidades e expectativas dos usuários em relação ao sistema.
- Projete a arquitetura do sistema, incluindo a escolha de tecnologias e plataformas a serem utilizadas.
- Desenvolva o sistema de acordo com o projeto arquitetural, criando módulos e funcionalidades específicas.
- Teste o sistema para garantir sua qualidade e correção.
- Implante o sistema em produção e forneça suporte e manutenção para garantir sua estabilidade e disponibilidade.

É importante ressaltar que a construção de um sistema de controle de cartões de crédito envolve questões complexas, como segurança e proteção de dados, além de aspectos legais e regulatórios. Portanto, é recomendável contar com profissionais especializados e experientes para garantir o sucesso do projeto.