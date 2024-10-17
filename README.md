# Bootcamp_Politicas_de_acesso
Este repositório fala um pouco sobre o que aprendi durante o modulo Gerenciando politicas de acessos do Bootcamp Microsoft Azure Essentials da Dio.

##  Azure Policy

O **Azure Policy** é uma ferramenta que permite garantir que os recursos no Azure estejam em conformidade com regras e padrões predefinidos. Ele ajuda a gerenciar e aplicar políticas de governança em toda a organização, permitindo definir limites sobre os tipos de recursos que podem ser criados e as configurações que podem ser aplicadas.

### Casos de Uso:
- **Compliance (Conformidade)**: Garantir que todos os recursos estejam em conformidade com as políticas de segurança e governança da empresa.
- **Padronização**: Assegurar que os recursos sigam um padrão específico, como nomes de recursos, locais de implantação e tags obrigatórias.
- **Segurança**: Impedir a criação de recursos em regiões não autorizadas ou o uso de tipos de máquina virtual específicos.

---

## Bloqueios de Recursos

Os **bloqueios de recursos** no Azure são usados para proteger recursos críticos contra exclusão ou modificação acidental. Existem dois tipos principais de bloqueios:
- **CanNotDelete**: Os recursos com esse bloqueio não podem ser excluídos, mas ainda podem ser modificados.
- **ReadOnly**: Os recursos são protegidos contra exclusão ou modificação, permitindo apenas operações de leitura.

### Casos de Uso:
- **Proteger Recursos Críticos**: Aplicar bloqueios em recursos essenciais, como máquinas virtuais em produção ou contas de armazenamento usadas para backups.
- **Evitar Exclusões Acidentais**: Garantir que recursos importantes não sejam excluídos inadvertidamente por administradores ou automações.

---

##  Portal de Confiança do Serviço

O **Portal de Confiança do Serviço** é uma plataforma da Microsoft que fornece informações detalhadas sobre a conformidade, segurança e privacidade dos serviços em nuvem. Ele ajuda os usuários a entender como a Microsoft gerencia a segurança e a privacidade de seus dados na nuvem.

### Casos de Uso:
- **Auditoria de Conformidade**: Fornecer relatórios e certificações para demonstrar conformidade com regulamentações como GDPR, HIPAA, e SOC.
- **Visibilidade sobre Segurança**: Entender as práticas de segurança que protegem os dados armazenados e processados nos serviços da Microsoft.

---

##  Microsoft Purview

O **Microsoft Purview** (anteriormente chamado de Azure Purview) é uma solução de governança de dados que oferece uma visão abrangente sobre os dados de uma organização, ajudando a descobrir, gerenciar e proteger dados em múltiplas plataformas.

### Casos de Uso:
- **Governança de Dados**: Gerenciar políticas de dados, metadados e segurança em toda a organização.
- **Classificação de Dados Sensíveis**: Identificar e categorizar dados confidenciais como informações pessoais (PII) ou dados financeiros.
- **Rastreamento de Linha de Dados**: Monitorar o ciclo de vida dos dados em diferentes sistemas para auditoria e conformidade.

---

# Exemplo Prático: Utilizando o Azure Policy e Adicionando Bloqueios

 **Acessar o Azure Policy**:
   - No [Azure Portal](https://portal.azure.com/), clique em **Política (Policy)** no menu à esquerda.
   - No painel de políticas, clique em **Criar Definição de Política** para definir uma nova regra de política.

 **Escolher uma Definição**:
   - Ao criar a política, você pode usar definições integradas ou criar uma nova.
   - Exemplo de Definição Integrada: Escolha a política **"Allowed Locations"** para restringir as regiões onde os recursos podem ser criados.

 **Configurar a Política**:
   - Defina um **nome** e **descrição** para a política.
   - Na seção **Parâmetros**, defina quais regiões serão permitidas. Por exemplo, você pode limitar a criação de recursos apenas na região "East US".

 **Atribuir a Política**:
   - Clique em **Atribuir** para aplicar a política.
   - Escolha o **escopo** (escopo de gerenciamento, assinatura ou grupo de recursos) onde a política será aplicada.
   - Defina a **exceção** (se houver), para recursos que não devem ser afetados pela política.

 **Testar a Política**:
   - Agora, qualquer tentativa de criar recursos fora das regiões permitidas pela política resultará em uma falha.

###  Aplicar Bloqueios a Recursos

 **Adicionar um Bloqueio**:
   - No painel do recurso, vá até a seção **Bloqueios** no menu à esquerda.
   - Clique em **Adicionar** para criar um novo bloqueio.

 **Configurar o Tipo de Bloqueio**:
   - Defina um **nome** para o bloqueio (como "Proteger VM").
   - Selecione o tipo de bloqueio:
     - **ReadOnly**: Apenas leitura; impede qualquer modificação ou exclusão do recurso.
     - **CanNotDelete**: O recurso não pode ser excluído, mas pode ser modificado.

 **Salvar o Bloqueio**:
   - Clique em **OK** para aplicar o bloqueio.
   - Agora, o recurso estará protegido de exclusão ou modificação, dependendo do tipo de bloqueio aplicado.

---



