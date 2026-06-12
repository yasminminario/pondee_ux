## Parte 1
1. O processo selecionado foi o fluxo de aprovação de Pull Requests (PRs), utilizado durante o desenvolvimento do projeto. O fluxo definido pelo grupo estabelece que todas as branches de desenvolvimento (feat/*, docs/*, etc.) devem ser integradas primeiro à branch develop. Apenas ao final da sprint a branch develop é integrada à main, garantindo maior controle sobre as entregas e evitando que funcionalidades incompletas sejam publicadas diretamente na versão principal do sistema. 
2.
<img width="609" height="137" alt="image" src="https://github.com/user-attachments/assets/581b87a2-1564-4362-9389-08331e150d94" />

<img width="601" height="130" alt="image" src="https://github.com/user-attachments/assets/577ecab5-7c55-4a17-9062-5d045f868012" />


3. O processo falhou durante o encerramento de uma sprint. Um integrante da equipe abriu um Pull Request apontando incorretamente para a branch main, quando o destino correto deveria ser develop. Durante a revisão, essa configuração passou despercebida e o merge foi aprovado.
Como consequência, o fluxo de versionamento definido pelo grupo foi quebrado. Tentamos corrigir o problema utilizando a funcionalidade de revert do GitLab. Entretanto, após o revert, ao reabrir o Pull Request corretamente, parte das alterações não foi reconhecida pela plataforma. Além disso, a integração posterior entre develop e main passou a indicar que não existiam mudanças pendentes, gerando inconsistências no histórico do repositório.
A solução adotada foi realizar um revert do próprio revert, restaurando o estado anterior e permitindo que o fluxo voltasse a funcionar normalmente.
Sob a ótica do framework REACH, o incidente impactou simultaneamente as métricas de Ability e Efficiency.
A métrica de Ability foi comprometida porque o processo dependia excessivamente da atenção manual dos revisores para validar aspectos operacionais básicos do Pull Request. Não existiam mecanismos automáticos ou checkpoints formais para impedir esse tipo de erro.
Já a métrica de Efficiency foi afetada porque uma atividade simples, aprovar uma entrega, gerou retrabalho, tempo adicional de investigação e múltiplas tentativas de correção.
A causa raiz não foi uma deficiência técnica da equipe, mas sim uma combinação entre erro humano e sobrecarga operacional. Como os merges ficaram acumulados para o último dia da sprint, a revisão foi realizada de forma mais apressada. Esse cenário foi agravado pela carga horária reduzida do módulo atual, que disponibiliza aproximadamente uma hora diária de desenvolvimento, exigindo uma adaptação significativa da equipe em relação aos módulos anteriores.
A principal lição aprendida foi que processos de DesignOps precisam considerar as limitações reais do contexto em que são aplicados. Um fluxo que depende exclusivamente de atenção humana tende a se tornar frágil quando a equipe está operando sob pressão de prazo.


## Parte 2
1. Durante o desenvolvimento da dashboard do projeto, realizamos uma validação direta com o parceiro para entender se as informações apresentadas eram realmente relevantes para o contexto de uso esperado. 

2. Feedback anotado e mandado no grupo de whatsapp do grupo:

<img width="1135" height="466" alt="image" src="https://github.com/user-attachments/assets/a9bb0242-42e9-494f-b543-6641d177c5ea" />

3. O feedback recebido foi incorporado ao backlog e transformado em decisões concretas de produto.
Entre os pontos levantados, três se destacaram:

### Adicionar fontes dos dados exibidos
Esse item foi considerado essencial para a confiabilidade da solução e foi priorizado para implementação ainda na Sprint 4. A funcionalidade foi registrada formalmente no backlog e tratada como requisito necessário para garantir transparência sobre a origem das informações apresentadas ao usuário.

### Conectar métricas com o backlog
Durante a discussão, identificamos que essa funcionalidade agregaria valor significativo ao produto, permitindo relacionar indicadores operacionais com métricas de desenvolvimento, como cycle time e outros indicadores de fluxo. Entretanto, por não ser essencial para a entrega principal, a funcionalidade foi planejada para a Sprint 5 como uma melhoria incremental.

### Modularidade do dashboard
Inicialmente a equipe considerou implementar a possibilidade de adicionar e remover métricas dinamicamente. Porém, durante o andamento da sprint, percebemos que o próprio parceiro atribuía maior relevância à esteira principal do projeto do que à dashboard em si.


Dessa forma, após reavaliar o valor da funcionalidade frente ao esforço necessário para desenvolvê-la, optamos por não implementá-la.
Sob a perspectiva do framework REACH, esse episódio contribuiu positivamente para a métrica de Clarity. O plano de DesignOps permitiu que a discussão deixasse de ser baseada apenas em preferências visuais e passasse a considerar prioridades de negócio, restrições de desenvolvimento e impacto esperado para o usuário.
Ao transformar o feedback em itens rastreáveis dentro do backlog, a equipe conseguiu alinhar expectativas entre desenvolvedores e parceiro, criando maior transparência sobre o que seria implementado, adiado ou descartado.
Por outro lado, a métrica de Results apresentou limitações. Embora o processo tenha ajudado a priorizar funcionalidades mais relevantes, não possuímos dados quantitativos suficientes para comprovar objetivamente o impacto das mudanças na experiência do usuário final.
Assim, o DesignOps foi eficaz para gerar clareza na tomada de decisão, mas teve capacidade limitada para demonstrar resultados concretos por meio de métricas de uso ou validações contínuas.

Segue print da lista de tarefas pra sprint 4 com inserção da fontes de dados no gráfico:

<img width="572" height="294" alt="image" src="https://github.com/user-attachments/assets/6c02fe9c-7ced-4902-9391-6e3cf979fa53" />


Segue print da lista de tarefas da print 5 com adição da implemtnação de backlog ligado à métricas:


<img width="551" height="103" alt="image" src="https://github.com/user-attachments/assets/6a1c71c7-f94b-463d-bc58-7b25f413e648" />


## Parte 3

1.e 2. Ao revisarmos criticamente o plano de DesignOps elaborado anteriormente, percebemos que algumas práticas documentadas estavam mais alinhadas a estruturas corporativas maduras do que à realidade de um time universitário.

O melhor exemplo foi a proposta de tornar a dashboard totalmente modular, permitindo que usuários adicionassem e removessem métricas livremente. Embora a ideia fosse tecnicamente interessante, ela introduzia uma complexidade de implementação significativa e demandaria esforço contínuo de manutenção.

A decisão de não implementar essa funcionalidade não ocorreu apenas por questões técnicas. Durante as discussões da equipe, avaliamos também fatores relacionados à disponibilidade, motivação e capacidade de execução dos integrantes.

Essa análise evidencia um aspecto frequentemente ignorado em processos de DesignOps: a saúde do time.

Ao longo do módulo, percebemos que parte da sobrecarga operacional vinha da tentativa de reproduzir práticas de mercado sem adaptar sua escala ao contexto acadêmico. O resultado era a criação de processos, cerimônias e controles que consumiam tempo considerável sem gerar valor proporcional para o projeto.

Sob a ótica da métrica Health, algumas práticas acabaram produzindo o efeito oposto ao desejado. Em vez de facilitar o desenvolvimento, aumentavam a sensação de burocracia e pressão sobre a equipe.

A principal autocrítica é que nosso plano superestimou a capacidade operacional do grupo. Com uma carga limitada de desenvolvimento diária e múltiplas entregas paralelas da faculdade, nem toda melhoria potencial justificava o investimento de tempo necessário para sua implementação.

Se o plano fosse reescrito hoje, cortaríamos ou simplificaríamos qualquer processo que não produzisse valor direto para o produto ou para a coordenação da equipe. A própria funcionalidade de modularidade do dashboard é um exemplo claro disso: apesar de tecnicamente interessante, geraria esforço adicional sem impacto proporcional nos objetivos principais do projeto.

A principal lição aprendida foi que DesignOps não deve ser utilizado para aumentar controle ou formalização. Seu objetivo deve ser reduzir atritos, preservar a capacidade produtiva da equipe e permitir que as pessoas foquem no desenvolvimento daquilo que realmente gera valor.
