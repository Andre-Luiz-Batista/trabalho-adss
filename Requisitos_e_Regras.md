# Regras de Negócio

---

## RN-001 — Cadastro obrigatório para uso da plataforma

**Título:**
Cadastro obrigatório para uso da plataforma.

**Descrição:**
Todo usuário deve possuir cadastro validado para utilizar qualquer serviço do app.

**Origem:**
Modelo de negócio da plataforma.

**Stakeholders envolvidos:**
Dono de pet, clínica veterinária, petshop, cuidador, transportador, motorista de entrega.

**Condição:**
Aplicada sempre que um usuário tentar solicitar, oferecer ou aceitar qualquer serviço no app.

**Regra:**
Nenhuma funcionalidade de solicitação, oferta ou aceite de serviço pode ser acessada por um usuário sem cadastro concluído e ativo.

**Exceções:**
Navegação em modo visitante é permitida apenas para consulta de informações públicas, sem realizar transações.

**Dados envolvidos:**
Nome, documento de identificação, contato, tipo de perfil, dados específicos do perfil.

**Prioridade:**
Crítica

**Status:**
Aprovado

**Requisitos relacionados:**
RF-001

**Observações:**

---

## RN-002 — Disponibilidade obrigatória para oferta de serviço

**Título:**
Prestadores devem declarar disponibilidade antes de receber solicitações.

**Descrição:**
Cuidadores, transportadores e motoristas de entrega somente recebem solicitações de serviço quando estiverem com disponibilidade declarada e ativa no app.

**Origem:**
Mapa de usuários.

**Stakeholders envolvidos:**
Cuidador, transportador, motorista de entrega, dono de pet.

**Condição:**
Aplicada sempre que o sistema buscar prestadores para uma nova solicitação.

**Regra:**
Um prestador sem disponibilidade ativa para o período/região da solicitação não deve ser listado como opção para o cliente.

**Exceções:**
Nenhuma.

**Dados envolvidos:**
Agenda de disponibilidade, região de atuação, status do prestador.

**Prioridade:**
Alta

**Status:**
Aprovado

**Requisitos relacionados:**
RF-006, RF-008

**Observações:**
—

---

## RN-003 — Limite de serviços simultâneos por prestador

**Título:**
Um prestador não pode aceitar dois serviços com horários conflitantes.

**Descrição:**
Cuidadores, transportadores e motoristas de entrega não podem ter dois compromissos aceitos que se sobreponham em data e horário.

**Origem:**
Necessidade operacional para evitar falhas na prestação do serviço.

**Stakeholders envolvidos:**
Cuidador, transportador, motorista de entrega, dono de pet, clínica parceira.

**Condição:**
Aplicada no momento em que um prestador tenta aceitar uma nova solicitação.

**Regra:**
O sistema deve impedir o aceite de uma solicitação cujo horário conflite com outro compromisso já confirmado do mesmo prestador.

**Exceções:**
Nenhuma.

**Dados envolvidos:**
Agenda de compromissos confirmados do prestador.

**Prioridade:**
Crítica

**Status:**
Aprovado

**Requisitos relacionados:**
RF-009

**Observações:**
—

---

## RN-004 — Agenda das clínicas veterinárias parceiras

**Título:**
Clínicas parceiras controlam sua própria agenda de atendimentos.

**Descrição:**
Cada clínica veterinária parceira define os tipos de atendimento oferecidos, duração e horários disponíveis, que ficam visíveis para agendamento pelos donos de pet.

**Origem:**
Mapa de usuários

**Stakeholders envolvidos:**
Clínica veterinária, dono de pet.

**Condição:**
Aplicada sempre que um horário for exibido como disponível para agendamento.

**Regra:**
Somente horários explicitamente liberados pela clínica podem ser reservados por um dono de pet.

**Exceções:**
Clínica pode bloquear horários emergencialmente, cancelando agendamentos futuros mediante notificação ao cliente.

**Dados envolvidos:**
Grade de horários, tipos de atendimento, duração por tipo, capacidade simultânea.

**Prioridade:**
Alta

**Status:**
Aprovado

**Requisitos relacionados:**
RF-004

**Observações:**
—

---

## RN-005 — Catálogo de produtos do petshop parceiro

**Título:**
Petshop parceiro controla seu próprio catálogo de produtos

**Descrição:**
Cada petshop parceiro é responsável por cadastrar, atualizar preço e manter o estoque dos produtos exibidos em sua estante virtual dentro do app.

**Origem:**
Mapa de usuários

**Stakeholders envolvidos:**
Petshop, dono de pet.

**Condição:**
Aplicada sempre que um produto for exibido para compra.

**Regra:**
Um produto sem estoque disponível não pode ser exibido como comprável; o preço exibido deve ser o vigente no momento da consulta.

**Exceções:**
Produtos sob encomenda podem ser exibidos com prazo de disponibilidade informado pelo petshop.

**Dados envolvidos:**
Catálogo de produtos, estoque, preço, petshop responsável.

**Prioridade:**
Alta

**Status:**
Aprovado

**Requisitos relacionados:**
RF-005

**Observações:**
—

---

## RN-006 — Validação documental de prestadores de serviço

**Título:**
Prestadores de serviço precisam de documentação aprovada antes de operar.

**Descrição:**
Clínicas, petshops, cuidadores, transportadores e motoristas de entrega somente podem oferecer serviços após a aprovação de documentos exigidos por perfil.

**Origem:**
Necessidade de segurança e conformidade da plataforma.

**Stakeholders envolvidos:**
Clínica, petshop, cuidador, transportador, motorista de entrega.

**Condição:**
Aplicada durante o processo de cadastro de um novo perfil de prestador.

**Regra:**
Um perfil de prestador permanece com status "Em análise" até que todos os documentos obrigatórios do seu tipo sejam aprovados pela equipe de validação da plataforma.

**Exceções:**
Nenhuma.

**Dados envolvidos:**
Documentos enviados, status de aprovação por documento, responsável pela validação.

**Prioridade:**
Crítica

**Status:**
Aprovado

**Requisitos relacionados:**
RF-001

**Observações:**
—

---

## RN-007 — Pagamento antecipado do serviço

**Título:**
Pagamento deve ser confirmado antes da execução do serviço.

**Descrição:**
Todo serviço contratado através do app deve ter o pagamento processado e confirmado antes de o prestador iniciar a execução.

**Origem:**
Modelo de negócio da plataforma.

**Stakeholders envolvidos:**
Dono de pet, clínica, petshop, cuidador, transportador, motorista de entrega.

**Condição:**
Aplicada no momento da confirmação de qualquer agendamento ou pedido.

**Regra:**
Um serviço não pode ser confirmado como "Agendado" enquanto o pagamento não estiver aprovado.

**Exceções:**
Clínicas parceiras podem optar por permitir pagamento presencial no estabelecimento, desde que configurado previamente como forma de pagamento aceita.

**Dados envolvidos:**
Forma de pagamento, valor do serviço, status da transação.

**Prioridade:**
Crítica

**Status:**
Aprovado

**Requisitos relacionados:**
RF-011

**Observações:**
—

---

## RN-008 — Avaliação obrigatória ao final do serviço

**Título:**
Usuários devem poder avaliar uns aos outros

**Descrição:**
Ao final de cada serviço executado, os usuários que interagiram entre si em um serviço devem avaliar uns aos outros.

**Origem:**
Necessidade de garantir qualidade e confiança da plataforma.

**Stakeholders envolvidos:**
Dono de pet, clínica, petshop, cuidador, transportador, motorista de entrega.

**Condição:**
Aplicada após a conclusão de um serviço.

**Regra:**
O sistema deve disponibilizar a opção de avaliação assim que o serviço for marcado como concluído, e os usuários devem ter sua reputação recalculada com base nas avaliações recebidas.

**Exceções:**

**Dados envolvidos:**
Nota, comentário, histórico de avaliações, média de reputação dos usuários.

**Prioridade:**
Média

**Status:**
Proposto

**Requisitos relacionados:**
RF-010

**Observações:**

---

# Requisitos Funcionais

## RF-001 — Avaliação entre Usuários

**Título:**  
Avaliação entre usuários

**Descrição:**  
O sistema deve permitir que usuários que tiveram contato entre si avaliem uns aos outros naquele determinado serviço

**Objetivo:**  
Manter a qualidade dos serviços prestados e evitar inconveniências entre usuários

**Stakeholders:**  
Todos os atores

**Ator principal:**  
Cliente

**Pré-condições:**  
- Usuários cadastrados
- Usuários tiveram contato através da contratação e prestação de um serviço
- Serviço marcado como concluído

**Entradas:**  
- Identificadores dos usuários
- Identificador do serviço
- Nota dentro de uma escala

**Processamento esperado:**  
Registrar a avaliação do serviço e dos usuários avaliados e atualizar a média de avaliação dos afetados.

**Saídas/Resultados:**  
Avaliação salva e refletida no perfil do usuário

**Pós-condições:**  
Serviço marcado como plenamente encerrado

**Fluxos alternativos/exceções:**  
- Prazo de avaliação expirar antes de ação por parte do usuário
- Avaliações ruins podem ser acrescidas de comentários e/ou denúncias

**Regras de negócio relacionadas:**  
RN-XXX

**Prioridade:**  
Média 

**Status:**  
Aprovado

**Critérios de aceite:**  
- A avaliação só pode ser feita por usuários relacionados num serviço e após a conclusão dele
- A média de avaliações deve ser recalculada automaticamente.

**Casos de uso relacionados:**  
UC-XXX

**Tarefas relacionadas:**  
TASK-XXX

**Casos de teste relacionados:**  
CT-XXX

## RF-002 — Cadastro de produtos e serviços

**Título:**  
Cadastro de produtos e serviços

**Descrição:**  
O sistema deve permitir que clínicas veterinárias e petshops cadastrem e ofertem seus produtos e serviços

**Objetivo:**  
Viabilização de vendas virtualmente

**Stakeholders:**  
Petshops, clínicas veterinárias

**Ator principal:**  
Petshops/Clínicias veterinárias

**Pré-condições:**  
Conta de parceiro aprovada

**Entradas:**  
Nome, descrição, preço, quantidade(para os produtos), disponibilidade (para os serviços)

**Processamento esperado:**  
Validar dados inseridos e vincular o produto/serviço ao parceiro

**Saídas/Resultados:**  
Produtos/serviços ficam disponíveis para consulta pelos clientes 

**Pós-condições:**  
Items aparecem no perfil do parceiro, nas buscas e sugestões

**Fluxos alternativos/exceções:**  
Dados obrigatórios faltando
Dados inválidos

**Regras de negócio relacionadas:**  
RN-XXX

**Prioridade:**  
Alta

**Status:**  
Aprovado

**Critérios de aceite:**  
- ...
- ...
- ...

**Casos de uso relacionados:**  
UC-XXX

**Tarefas relacionadas:**  
TASK-XXX

**Casos de teste relacionados:**  
CT-XXX

## RF-003 — Cadastro de disponibilidade de cuidador

**Título:**  
Cadastro de disponibilidade de cuidador

**Descrição:**  
O sistema deve permitir que cuidadores cadastrem as datas e horários que tem disponíveis juntamente do tipo de serviço(cuidar, passear, etc)

**Objetivo:**  
Expor os serviços de um cuidador para clientes interessados

**Stakeholders:**  
Cuidadores, donos de pet

**Ator principal:**  
Cuidadores

**Pré-condições:**  
Conta de cuidador parceiro aprovada

**Entradas:**  
Dados necessários.

**Processamento esperado:**  
O que o sistema deve realizar?

**Saídas/Resultados:**  
Qual resultado deve ser produzido?

**Pós-condições:**  
Qual deve ser o estado do sistema após a execução?

**Fluxos alternativos/exceções:**  
Quais comportamentos diferentes podem ocorrer?

**Regras de negócio relacionadas:**  
RN-XXX

**Prioridade:**  
Crítica | Alta | Média | Baixa

**Status:**  
Proposto | Em análise | Aprovado | Em desenvolvimento | Implementado | Validado

**Critérios de aceite:**  
- ...
- ...
- ...

**Casos de uso relacionados:**  
UC-XXX

**Tarefas relacionadas:**  
TASK-XXX

**Casos de teste relacionados:**  
CT-XXX




# Requisitos Não Funcionais

## RNF-001 — Tempo de resposta na busca de prestadores

**Categoria:**
Desempenho

**Descrição:**
O sistema deve apresentar a lista de prestadores disponíveis (transportadores, cuidadores, motoristas) em até 3 segundos para 95% das buscas realizadas sob a carga operacional definida.

**Justificativa:**
A experiência de uso de um app de marcar serviços sob demanda depende de resposta rápida para retenção do usuário.

**Métrica/Critério mensurável:**
Tempo entre o envio da busca por prestadores e a exibição da lista de parceiros, medido em ambiente de carga simulada equivalente ao pico de uso proposto.

**Escopo:**
Funcionalidades de busca de prestadores (RF-002, RF-006, RF-008).

**Prioridade:**
Alta

**Status:**
Aprovado

**Requisitos relacionados:**
RF-002, RF-006, RF-008

**Casos de teste relacionados:**
CT-XXX

---

## RNF-002 — Segurança dos dados de pagamento

**Categoria:**
Segurança

**Descrição:**
O sistema não deve armazenar dados sensíveis de cartão de pagamento diretamente em seus próprio banco de dados, de forma segura.

**Justificativa:**
Reduzir a exposição da plataforma a riscos de vazamento de dados financeiros e cumprir exigências regulatórias da função de pagamentos.

**Métrica/Critério mensurável:**
Ausência de dados de cartão em evidência nos bancos da aplicação.

**Escopo:**
Todo o fluxo de pagamento (RF-011).

**Prioridade:**
Crítica

**Status:**
Aprovado

**Requisitos relacionados:**
RF-011

**Casos de teste relacionados:**
CT-XXX

---


## RNF-003 — Disponibilidade da plataforma

**Categoria:**
Disponibilidade

**Descrição:**
O sistema deve manter disponibilidade mínima de 99,5% em base mensal, considerando as funcionalidades essenciais de solicitação e aceite de serviços.

**Justificativa:**
Indisponibilidade impede diretamente donos de pets de solicitarem serviços em situações potencialmente urgentes.

**Métrica/Critério mensurável:**
Percentual mensal medido por ferramenta de monitoramento, excluindo janelas de manutenção programada.

**Escopo:**
Todo o sistema.

**Prioridade:**
Crítica

**Status:**
Aprovado

**Requisitos relacionados:**
RF-002, RF-009, RF-011

**Casos de teste relacionados:**
CT-XXX

---

## RNF-004 — Usabilidade do aplicativo móvel

**Categoria:**
Usabilidade

**Descrição:**
Um novo usuário do app deve conseguir concluir a solicitação de transporte de pet (RF-002) em no máximo 5 etapas.

**Justificativa:**
O público-alvo inclui donos de pets com rotina corrida, que precisam de um fluxo simples e rápido de contratação.

**Métrica/Critério mensurável:**
Teste de usabilidade com usuários reais medindo número de etapas e taxa de conclusão sem assistência.

**Escopo:**
Fluxo de solicitação de serviços (RF-002, RF-003, RF-004).

**Prioridade:**
Alta

**Status:**
Aprovado

**Requisitos relacionados:**
RF-002, RF-003, RF-004

**Casos de teste relacionados:**
CT-XXX

---

## RNF-005 — Escalabilidade por região de operação

**Categoria:**
Escalabilidade

**Descrição:**
O sistema deve suportar a expansão para novas regiões sem necessidade de alterações estruturais no código, apenas configuração de novas áreas de cobertura.

**Justificativa:**
O modelo de negócio prevê crescimento por regiões, com transportadores, motoristas, clínicas e petshops distintos por localidade.

**Métrica/Critério mensurável:**
Tempo necessário para ativar uma nova região operacional via configuração.

**Escopo:**
Módulos de cobertura regional (RN-008) e busca de prestadores.

**Prioridade:**
Média

**Status:**
Aprovado

**Requisitos relacionados:**
RF-002, RF-008

**Casos de teste relacionados:**
CT-XXX

---

## RNF-006 — Confiabilidade no cálculo de conflitos de agenda

**Categoria:**
Confiabilidade

**Descrição:**
O sistema deve garantir consistência na verificação de conflitos de horário entre solicitações, mesmo sob acessos concorrentes de múltiplos clientes tentando reservar o mesmo prestador simultaneamente.

**Justificativa:**
Falhas de concorrência podem gerar dupla reserva do mesmo prestador, prejudicando a confiança na plataforma.

**Métrica/Critério mensurável:**
Zero ocorrências de dupla reserva em testes sobre o mesmo horário/prestador.

**Escopo:**
Aceite de solicitações (RF-009) e agendamentos em clínicas (RF-004).

**Prioridade:**
Crítica

**Status:**
Aprovado

**Requisitos relacionados:**
RF-004, RF-009

**Casos de teste relacionados:**
CT-XXX

## RNF-001 — Processamento de Serviços

**Categoria:**  
Desempenho

**Descrição:**  
O sistema deve permitir um cadastro de consulta

**Justificativa:**  
Por que este requisito é necessário?

**Métrica/Critério mensurável:**  
Como será verificado?

**Escopo:**  
Todo o sistema ou funcionalidades específicas?

**Prioridade:**  
Crítica | Alta | Média | Baixa

**Status:**  
Proposto | Em análise | Aprovado | Implementado | Validado

**Requisitos relacionados:**  
RF-XXX

**Casos de teste relacionados:**  
CT-XXX

---

## RNF-XXX — Nome do Requisito

**Categoria:**  
Segurança | Desempenho | Usabilidade | ...

**Descrição:**  
O sistema deve...

**Justificativa:**  
Por que este requisito é necessário?

**Métrica/Critério mensurável:**  
Como será verificado?

**Escopo:**  
Todo o sistema ou funcionalidades específicas?

**Prioridade:**  
Crítica | Alta | Média | Baixa

**Status:**  
Proposto | Em análise | Aprovado | Implementado | Validado

**Requisitos relacionados:**  
RF-XXX

**Casos de teste relacionados:**  
CT-XXX
