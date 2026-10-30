# Levantamento — RedFit (unidade Neo Química Arena)

> Documento escrito pelo grupo com o que foi levantado na organização. Trechos marcados com **PREENCHER** dependem de informações que só quem esteve no local pode registrar.

## 1. Identificação

| Item | Registro |
|---|---|
| Organização | RedFit — rede de academias (26 unidades) |
| Unidade estudada | Neo Química Arena — Av. Miguel Ignácio Curi, 111, 10º andar, Itaquera, São Paulo – SP, CEP 08220-000 |
| Entrevistado | Guilherme Nogueira, gerente da unidade |
| Telefone do responsável | +55 (11) 93622-0732 |
| Data e local | 16/09/2026, na própria unidade |
| Participantes do grupo | Cauã Macedo Santana, Gustavo Totino, Marco Aurélio Lira, Pedro Henrique Silva, Suellen Pimenta |
| Foto da entrevista | `evidencias/` — ** Prencher Imagem PNG ou JPEG **|
| Vínculo com o grupo | Um integrante frequenta a unidade diariamente e é amigo do gerente |

## 2. Informado pelo entrevistado (respostas)

**Equipe e porte**
- A unidade tem 2 gerentes, 2 recepcionistas e 6 instrutores.
- Cerca de 2.350 alunos ativos e cerca de 700 alunos por dia.

**Planos e cobrança**
- Planos FIT (R$ 119,90 por mês; matrícula de R$ 49,90 cobrada só no primeiro mês; fidelidade com multa equivalente às mensalidades restantes; acesso a qualquer unidade), RED (R$ 99,90 por mês; sem matrícula) e Anual (R$ 89,90 por mês; fidelidade com multa equivalente às mensalidades restantes; acesso a qualquer unidade).
- Pagamento por cartão de crédito, cartão de débito ou boleto enviado por e-mail.
- Não é permitido levar amigos como acompanhantes.

**Acesso**
- O acesso é por reconhecimento facial, que bloqueia quem está com a mensalidade em atraso.
- O único parceiro de acesso é o TotalPass.
- Nos horários de pico as catracas travam e formam filas.

**Cadastro, saúde e treino**
- O cadastro tem CPF, nome, data de nascimento (para saber se é menor), endereço (proximidade e emergência) e telefone.
- Menor de idade só treina com o responsável.
- O aluno preenche uma ficha com informações médicas, em papel.
- Há avaliação física (peso, gordura corporal, gordura visceral, água e massa muscular) feita por instrutor; treinos montados por instrutor; instrutores com CREF.
- Equipamentos citados: cabo/polia, remada articulada, banco inclinado, banco reto, leg press e cadeira extensora.
- A unidade não tem aulas para agendamento.
- Exclusões são feitas por gerentes; alterações por gerentes e recepção.

## 3. Observado presencialmente (separado das respostas)

**PREENCHER** com o que o grupo viu acontecer no local, por exemplo:
- como é a entrada e o funcionamento da catraca no horário de pico;
- como a recepção cadastra o aluno e onde a ficha de papel é guardada;
- como o instrutor registra a avaliação e o treino;
- que equipamentos e quantidades há no salão.

## 4. Pesquisa de processos, requisitos e regras típicos de academias (com apoio de IA)

O grupo usou IA para listar processos, requisitos e regras comuns em academias e conferiu o que se aplica à RedFit (ver seção 6 do README). Itens típicos que **não** apareceram na entrevista e ficaram fora do modelo, a confirmar com o gerente: compra e manutenção de equipamentos, cancelamento de plano em detalhe, atestado médico, controle de armários. **PREENCHER** o que foi confirmado em nova conversa.

## 5. Hipóteses assumidas no modelo (a validar com o gerente)

| Hipótese | Onde aparece |
|---|---|
| A abrangência do plano RED não foi informada | PLANO.TP_MODALIDADE = `A_CONFIRMAR` |
| A ficha de saúde em papel é registrada no sistema pela recepção | Processo de cadastro e matrícula |
| Mensalidade tem situação PAGO ou PENDENTE; o atraso é calculado pelo vencimento | PAGAMENTO.TP_STATUS |
| O aluno se vincula a uma unidade de matrícula | ALUNO.ID_UNIDADE |
| Gerentes, recepcionistas e instrutores pertencem a uma unidade | RN23 |
| Medidas em kg, % e segundos | AVALIACAO_FISICA, ITEM_TREINO |
| A classificação do treino (TP_TREINO) é definida pela RedFit | TREINO.TP_TREINO |
| Como o aluno do TotalPass é cadastrado na RedFit (tem plano?) | CHECK_IN.TP_ACESSO |

## 6. Perguntas para uma nova visita

1. Quantos pagamentos por mês, qual a proporção entre cartão e boleto e qual a inadimplência?
2. Quantas catracas há e em que horários o travamento é mais frequente?
3. A ficha médica continua em papel? Quem a registra no sistema?
4. Como funciona o cancelamento do plano e a cobrança da multa?
5. A academia exige atestado médico?
6. O aluno do TotalPass tem plano na RedFit?
7. O plano RED vale em quais unidades?
8. Quantos aparelhos de cada tipo a unidade tem?
