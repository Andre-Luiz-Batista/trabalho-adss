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

## RN-008 — Avaliação do serviço

**Título:**
Usuários devem poder avaliar uns aos outros

**Descrição:**
Ao final de cada serviço executado, os usuários que interagiram entre si em um serviço podem avaliar uns aos outros.

**Origem:**
Necessidade de garantir qualidade e confiança da plataforma.

**Stakeholders envolvidos:**
Dono de pet, clínica, petshop, cuidador, transportador, motorista de entrega.

**Condição:**
Aplicada após a conclusão de um serviço.

**Regra:**
O sistema deve disponibilizar a opção de avaliação assim que o serviço for marcado como concluído, e os usuários devem ter sua reputação recalculada com base nas avaliações recebidas.

**Exceções:**
Nenhuma.

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

## RF-001 — Solicitar transporte de pet para o veterinário

**Título:**
Solicitação de transporte de pet.

**Descrição:**
O sistema deve permitir que o dono de pet solicite o transporte de seu animal até uma clínica veterinária, informando origem, destino e horário desejado.

**Objetivo:**
Resolver a falta de disponibilidade do dono de pet para locomoção até o veterinário.

**Stakeholders:**
Dono de pet, transportador parceiro.

**Ator principal:**
Dono de pet.

**Pré-condições:**
- Usuário cadastrado e ativo.
- Endereço de origem e destino informados.

**Entradas:**
Endereço de origem, endereço de destino, horário desejado, dados do pet.

**Processamento esperado:**
O sistema deve buscar transportadores parceiros com disponibilidade e cobertura para a rota e horário solicitados, exibindo opções ao cliente.

**Saídas/Resultados:**
Lista de transportadores disponíveis com valor estimado do serviço.

**Pós-condições:**
Solicitação registrada, aguardando confirmação do cliente e aceite do transportador.

**Fluxos alternativos/exceções:**
- Nenhum transportador disponível na região/horário.
- Cliente cancela a solicitação antes da confirmação.

**Regras de negócio relacionadas:**


**Prioridade:**
Crítica

**Status:**
Aprovado

**Critérios de aceite:**
- Exibir apenas transportadores com disponibilidade e cobertura compatíveis.
- Exibir valor estimado antes da confirmação.
- Permitir cancelamento antes do aceite do transportador.

**Casos de uso relacionados:**

**Tarefas relacionadas:**

**Casos de teste relacionados:**

---

## RF-002 — Comprar e receber produtos pet

**Título:**
Compra e entrega de produtos pet.

**Descrição:**
O sistema deve permitir que o dono de pet compre produtos disponíveis na estante virtual de um petshop parceiro e solicite a entrega em seu endereço.

**Objetivo:**
Permitir a compra de acessórios, brinquedos e alimentação sem necessidade de deslocamento do cliente.

**Stakeholders:**
Dono de pet, petshop, motorista de entrega.

**Ator principal:**
Dono de pet.

**Pré-condições:**
- Produto disponível em estoque.
- Endereço de entrega cadastrado.

**Entradas:**
Produtos selecionados, quantidade, endereço de entrega, forma de pagamento.

**Processamento esperado:**
O sistema deve confirmar o pedido junto ao petshop, processar o pagamento e buscar um motorista de entrega disponível na região.

**Saídas/Resultados:**
Pedido confirmado, motorista designado, previsão de entrega informada.

**Pós-condições:**
Estoque do produto atualizado; pedido em andamento até confirmação de entrega.

**Fluxos alternativos/exceções:**
- Produto fica indisponível entre a seleção e a confirmação.
- Nenhum motorista disponível na região.

**Regras de negócio relacionadas:**

**Prioridade:**
Alta

**Status:**
Aprovado

**Critérios de aceite:**
- Impedir finalização de compra de produto sem estoque.
- Atualizar estoque somente após confirmação do pagamento.
- Notificar cliente sobre status do pedido.

**Casos de uso relacionados:**

**Tarefas relacionadas:**

**Casos de teste relacionados:**

---

## RF-003 — Agendar atendimento em clínica veterinária parceira

**Título:**
Agendamento de consulta, tosa ou atendimento.

**Descrição:**
O sistema deve permitir que o dono de pet visualize horários disponíveis de uma clínica parceira e agende um atendimento.

**Objetivo:**
Viabilizar a venda de serviços das clínicas parceiras através do app.

**Stakeholders:**
Dono de pet, clínica veterinária.

**Ator principal:**
Dono de pet.

**Pré-condições:**
- Clínica com agenda ativa e horários liberados.
- Usuário cadastrado.

**Entradas:**
Clínica selecionada, tipo de atendimento, horário desejado, dados do pet.

**Processamento esperado:**
O sistema deve verificar a disponibilidade do horário na agenda da clínica e reservá-lo mediante confirmação de pagamento.

**Saídas/Resultados:**
Agendamento confirmado e refletido na agenda da clínica.

**Pós-condições:**
Horário reservado torna-se indisponível para outros clientes.

**Fluxos alternativos/exceções:**
- Horário torna-se indisponível durante a reserva.
- Clínica cancela o horário emergencialmente.

**Regras de negócio relacionadas:**

**Prioridade:**
Alta

**Status:**
Aprovado

**Critérios de aceite:**
- Impedir dupla reserva do mesmo horário.
- Notificar cliente e clínica após confirmação.
- Permitir que a clínica cancele com notificação automática ao cliente.

**Casos de uso relacionados:**

**Tarefas relacionadas:**

**Casos de teste relacionados:**

---

## RF-004 — Gerenciar estante virtual de produtos

**Título:**
Gestão do catálogo de produtos do petshop.

**Descrição:**
O sistema deve permitir que o petshop parceiro cadastre, edite, remova e controle o estoque dos produtos exibidos em sua estante virtual.

**Objetivo:**
Viabilizar a venda dos produtos do petshop no meio virtual.

**Stakeholders:**
Petshop.

**Ator principal:**
Petshop parceiro.

**Pré-condições:**
Perfil de petshop aprovado e ativo.

**Entradas:**
Nome do produto, categoria, descrição, preço, quantidade em estoque, imagens.

**Processamento esperado:**
O sistema deve validar os dados do produto e atualizar o catálogo exibido aos clientes em tempo real.

**Saídas/Resultados:**
Produto disponível na estante virtual do petshop.

**Pós-condições:**
Catálogo do petshop atualizado.

**Fluxos alternativos/exceções:**
- Produto com estoque zerado é automaticamente ocultado da compra.
- Petshop tenta cadastrar produto com dados incompletos.

**Regras de negócio relacionadas:**

**Prioridade:**
Alta

**Status:**
Aprovado

**Critérios de aceite:**
- Impedir publicação de produto sem preço ou sem estoque informado.
- Refletir alterações de estoque em tempo real na vitrine.

**Casos de uso relacionados:**

**Tarefas relacionadas:**

**Casos de teste relacionados:**

---

## RF-005 — Cadastrar disponibilidade de cuidador

**Título:**
Cadastro de disponibilidade do cuidador parceiro.

**Descrição:**
O sistema deve permitir que o cuidador parceiro informe dias, horários, locais de atendimento e observações sobre os cuidados que presta.

**Objetivo:**
Permitir que o cuidador se ofereça como prestador de serviço pelo app.

**Stakeholders:**
Cuidador.

**Ator principal:**
Cuidador parceiro.

**Pré-condições:**
Perfil de cuidador aprovado.

**Entradas:**
Dias e horários disponíveis, região de atendimento, tipos de cuidado oferecidos, observações.

**Processamento esperado:**
O sistema deve armazenar a disponibilidade e utilizá-la na busca por cuidadores para novas solicitações.

**Saídas/Resultados:**
Agenda de disponibilidade do cuidador atualizada e visível para clientes na busca.

**Pós-condições:**
Cuidador passa a ser elegível para solicitações compatíveis.

**Fluxos alternativos/exceções:**
Cuidador remove disponibilidade previamente cadastrada.

**Regras de negócio relacionadas:**

**Prioridade:**
Alta

**Status:**
Aprovado

**Critérios de aceite:**
- Não listar cuidador fora dos dias/horários declarados.
- Permitir edição e remoção da disponibilidade a qualquer momento.

**Casos de uso relacionados:**

**Tarefas relacionadas:**

**Casos de teste relacionados:**

---

## RF-006 — Contratar transporte vinculado a atendimento de cuidador

**Título:**
Contratação de transporte para cuidador em atendimento externo.

**Descrição:**
O sistema deve permitir que, ao confirmar um atendimento de cuidado em local distante de sua residência, o cuidador contrate um transportador ou motorista parceiro para o deslocamento no horário do serviço.

**Objetivo:**
Viabilizar o deslocamento do cuidador até locais de atendimento distantes.

**Stakeholders:**
Cuidador, transportador/motorista parceiro, dono de pet.

**Ator principal:**
Cuidador parceiro.

**Pré-condições:**
- Agendamento de cuidado confirmado.
- Distância entre residência do cuidador e local do atendimento calculada.

**Entradas:**
Endereço de origem, endereço de destino, horário do serviço.

**Processamento esperado:**
O sistema deve oferecer a contratação de transporte antes de confirmar o agendamento de cuidado.

**Saídas/Resultados:**
Transporte reservado e vinculado ao horário do atendimento de cuidado.

**Pós-condições:**
Agendamento de cuidado só é confirmado após a garantia do deslocamento.

**Fluxos alternativos/exceções:**
- Cuidador informa transporte próprio.
- Nenhum transportador disponível para o horário necessário.

**Regras de negócio relacionadas:**

**Prioridade:**
Alta

**Status:**
Proposto

**Critérios de aceite:**
- Calcular corretamente a distância entre residência do cuidador e local do atendimento.
- Impedir confirmação do atendimento sem transporte garantido, quando aplicável.

**Casos de uso relacionados:**

**Tarefas relacionadas:**

**Casos de teste relacionados:**

---

## RF-007 — Cadastrar disponibilidade de transportador/motorista

**Título:**
Cadastro de disponibilidade de transportadores e motoristas parceiros.

**Descrição:**
O sistema deve permitir que transportadores parceiros e motoristas parceiros informem horários, datas e região de cobertura em que estão disponíveis para atender solicitações.

**Objetivo:**
Permitir que motoristas com espaço no veículo se ofereçam como prestadores de transporte ou entrega.

**Stakeholders:**
Transportador, motorista de entrega.

**Ator principal:**
Transportador/motorista parceiro.

**Pré-condições:**
Perfil aprovado com documentação e veículo validados.

**Entradas:**
Dias e horários disponíveis, região de cobertura, tipo de serviço oferecido.

**Processamento esperado:**
O sistema deve armazenar a disponibilidade declarada e utilizá-la na busca de prestadores para novas solicitações de transporte ou entrega.

**Saídas/Resultados:**
Prestador elegível para receber solicitações compatíveis com sua disponibilidade e cobertura.

**Pós-condições:**
—

**Fluxos alternativos/exceções:**
Prestador altera ou remove disponibilidade previamente cadastrada.

**Regras de negócio relacionadas:**

**Prioridade:**
Alta

**Status:**
Aprovado

**Critérios de aceite:**
- Não oferecer solicitações fora da cobertura declarada.
- Permitir edição da disponibilidade a qualquer momento.

**Casos de uso relacionados:**

**Tarefas relacionadas:**

**Casos de teste relacionados:**

---

## RF-008 — Aceitar/recusar solicitação de serviço

**Título:**
Aceite de solicitação por prestador.

**Descrição:**
O sistema deve permitir que o prestador aceite ou recuse uma solicitação de serviço recebida

**Objetivo:**
Formalizar o compromisso entre cliente e prestador para execução do serviço.

**Stakeholders:**
Dono de pet, cuidador, transportador, motorista de entrega, clínica.

**Ator principal:**
Prestador de serviço.

**Pré-condições:**
Solicitação pendente de aceite dentro da disponibilidade do prestador.

**Entradas:**
Decisão do prestador.

**Processamento esperado:**
O sistema deve validar se o horário da solicitação conflita com outro compromisso já confirmado do prestador antes de permitir o aceite.

**Saídas/Resultados:**
Serviço confirmado ou liberado para outro prestador.

**Pós-condições:**
Compromisso adicionado à agenda do prestador, em caso de aceite.

**Fluxos alternativos/exceções:**
- Prestador tenta aceitar solicitação com conflito de horário.
- Solicitação expira sem resposta do prestador.

**Regras de negócio relacionadas:**

**Prioridade:**
Crítica

**Status:**
Aprovado

**Critérios de aceite:**
- Bloquear aceite de solicitações com conflito de horário.
- Notificar o cliente imediatamente após o aceite ou recusa.

**Casos de uso relacionados:**

**Tarefas relacionadas:**

**Casos de teste relacionados:**

---

## RF-009 — Avaliar serviço prestado

**Título:**
Avaliação entre usuários após a conclusão do serviço.

**Descrição:**
O sistema deve permitir que os usuários se avaliem entre si ao final de cada serviço concluído.

**Objetivo:**
Manter a qualidade e a confiança na rede de prestadores parceiros.

**Stakeholders:**
Dono de pet, clínica, petshop, cuidador, transportador, motorista de entrega.

**Ator principal:**
Dono de pet.

**Pré-condições:**
Serviço marcado como concluído.

**Entradas:**
Nota, comentário.

**Processamento esperado:**
O sistema deve registrar a avaliação e recalcular a reputação média dos usuários.

**Saídas/Resultados:**
Reputação dos usuários atualizada.

**Pós-condições:**
Avaliação disponível no histórico.

**Fluxos alternativos/exceções:**
Cliente opta por não avaliar dentro do prazo definido.

**Regras de negócio relacionadas:**

**Prioridade:**
Média

**Status:**
Proposto

**Critérios de aceite:**
- Disponibilizar avaliação apenas para serviços concluídos.
- Atualizar a reputação do prestador imediatamente após o envio da avaliação.

**Casos de uso relacionados:**

**Tarefas relacionadas:**

**Casos de teste relacionados:**

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

---

## RNF-007 — Privacidade de conversas privadas

**Categoria:**  
Legal

**Descrição:**  
O sistema deve manter privacidade para os conteúdos compartilhados e comunicados entre Donos de Pet, Cuidadores, Transportadores e Motoristas parceiros.

**Justificativa:**  
Para estar de acordo com a LGPD, garantindo segurança para os usuários.

**Métrica/Critério mensurável:**  
Avaliação dos dados armazenados e seu englobamento nos requisitos da LGPD.

**Escopo:**  
Conversas privadas entre os prestadores envolvidos.

**Prioridade:**
Alta

**Status:**
Aprovado

**Requisitos relacionados:**  

**Casos de teste relacionados:**  
