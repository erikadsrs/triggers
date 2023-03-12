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

