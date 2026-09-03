# Regras de Negócio



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