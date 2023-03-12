# triggers
Estudos em Triggers

Triggers são gatilhos, executáveis em registros, antes ou depois da DML (insert, update, upsert, delete, undelete, merge), tal qual um Flow.

Pode ser usadas em regras de barramentos, criação de registros, integrações, validação de campos de layouts, validação de registros de cargas etc.

Passo a Passo
Create Apex Trigger > Convenção para Name : ObjectTrigger.trigger 

Sintaxe
trigger TriggerName on Object (events)

Events são before insert, after insert e assim em diante

Exemplo
Validação de Número de Telefone durante a inserção de uma Conta

Boa Prática
Uso de Listas e Maps 

Contextos das Triggers
new = lista atual de resgistros
old = lista de registros antigos 
newMap = 
oldMap = 
.isExecuting = 
.size = 
.operationType = 
System.TriggerOperation.Method.AFTER_EVENT = 

Ordem de Execução de Salvamento de Registro (fluxo)
Pode gerar impacto no que eu preciso fazer, por isso, entender e determinar de forma correta. Principalmente, quando temos outros códigos/automações rodando juntos

before = antes de ser incluído na base
after = depois de ser incluído na base

1° Carrega o registro atual na base 

2° System Validation Rules (layout)

3° Triggers Before Events *

4° Custom Validation Rules *

5° Duplicate Rules 

6° Salva o registro, MAS, não persiste (não insere totalmente)

7° Triggers After Events *

8° Assignments Rules (pode alterar registros, como owners etc)

9° Auto-response (Web-To-Case + Template Email)

10° Workflow Rules *

11° Escalation Rules (Escalonamento de Casos)

12° Entiltlement Rules (Direitos, Processos de Habilitação e SLA)

13° Roll-up Fields (serão recalculados ou dispararão recalculagens)

14° Sharing Evaluations (liberações para perfis, usuários etc)

15° Persiste o dado na base

16° Post logic Process (envio de emails por exemplo)

