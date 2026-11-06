# Levantamento — RedFit (unidade Neo Química Arena)

> Documento escrito pelo grupo com o que foi levantado na organização.
> **Números de negócio congelados em 06/11/2026** (fonte da verdade alinhada ao README / RN19 / `docs/script.sql`).
> Onde a entrevista inicial divergiu da página de planos ou da 2ª entrevista, prevalece a decisão congelada abaixo.

## 1. Identificação

| Item | Registro |
|---|---|
| Organização | RedFit — rede de academias (**23 unidades**) |
| Unidade estudada | Neo Química Arena — Av. Miguel Ignácio Curi, 111, 10º andar, Itaquera, São Paulo – SP, CEP 08220-000 |
| Entrevistado | Guilherme Nogueira, gerente da unidade |
| Telefone do responsável | +55 (11) 93622-0732 |
| Data e local | Entrevistas em 31/08/2026 e 30/10/2026, na própria unidade |
| Participantes do grupo | Cauã Macedo Santana, Gustavo Totino, Marco Aurélio Lira, Pedro Henrique Silva, Suellen Pimenta |
| Foto da entrevista | `evidencias/entrevista.png` |
| Vínculo com o grupo | Um integrante frequenta a unidade diariamente e é amigo do gerente |

## 2. Informado pelo entrevistado (respostas) — com valores congelados

**Equipe e porte (congelado)**
- A unidade tem **2 gerentes, 2 recepcionistas e 4 instrutores** (e equipe de limpeza fora do escopo do banco).
- Estimativa informada: cerca de **2.500 alunos ativos** e cerca de **500 alunos por dia** (não é contagem extraída do sistema).

**Planos e cobrança (congelado — RN19 / página + confirmação do gerente)**
| Plano | Mensalidade | 1º mês / matrícula | Fidelidade | Bloqueia atraso | Amigos |
|---|---|---|---|---|---|
| RED | R$ **139,90** | R$ **9,90** no 1º mês; matrícula grátis | Não (aviso 30 dias) | **Sim** | 5 |
| ANUAL | R$ **89,90** | Matrícula R$ **49,90** | 12 meses (multa = mensalidades restantes) | Não | 5 |
| FIT | R$ **119,90** | Matrícula R$ **49,90** | 12 meses (multa 20% meses restantes) | Não | 0 |

- Pagamento **recorrente**: cartão de **crédito** (renovação automática).
- Na recepção (avulsos): apenas **Pix** e **débito**. **Não há boleto** (decisão congelada; a menção a boleto na 1ª conversa foi descartada).
- Benefícios corporativos / parceiros de acesso: Wellhub, TotalPass e Gurupass.

**Acesso**
- Check-in por **digital** ou **reconhecimento facial**; parceiros exigem autorização na unidade.
- No plano RED, mensalidade em atraso bloqueia a catraca; nos demais, só pendência.

**Cadastro, saúde e treino**
- Cadastro: CPF, nome, data de nascimento, endereço, telefone (e-mail opcional).
- Menor de idade só treina com responsável (regra operacional; não imposta pelo SGBD).
- Prontuário: problemas cardíaco, ósseo, respiratório; doenças hereditárias; medicamentos.
- Avaliação física (bioimpedância): peso, gordura corporal, gordura visceral, água, massa muscular.
- Treinos montados por instrutor (CREF); equipamentos citados: cabo/polia, remada articulada, banco inclinado, banco reto, leg press, cadeira extensora.
- Sem aulas coletivas / agendamento nesta unidade.
- Exclusões: gerentes; alterações de cadastro: gerentes e recepção.

## 3. Observado presencialmente

- Dificuldade / travamentos no registro de Face ID.
- Software atual: consultas fragmentadas (plano, pagamento e treino não vistos juntos).
- Detalhes adicionais de observação de catraca e quantidades de aparelhos podem ser ampliados em visita futura.

## 4. Pesquisa de processos típicos

Itens típicos de academias **fora do escopo** deste modelo (não confirmados como processo da unidade ou não prioritários): compra/manutenção de equipamentos, atestado médico obrigatório, controle de armários, detalhamento completo de cancelamento além das multas de fidelidade.

## 5. Hipóteses assumidas no modelo (validadas ou descartadas)

| Hipótese | Decisão |
|---|---|
| Abrangência RED / Anual = todas as unidades; FIT com treino exclusivo na unidade de compra | Congelado em `PLANO.DS_ABRANGENCIA` |
| Ficha de saúde registrada no sistema (além do papel) | Modelado em `PRONTUARIO_SAUDE` (+ doenças/medicamentos) |
| Atraso = `ST_PAGAMENTO = 'PENDENTE'` com vencimento passado | Sim (derivado; não há coluna “em atraso”) |
| Aluno vinculado a unidade de matrícula | `ALUNO.ID_UNIDADE` |
| Funcionários por unidade | `ID_UNIDADE` em GERENTE, RECEPCIONISTA, INSTRUTOR |
| Sem tabela CONTRATO | Vínculo em `ALUNO` (`ID_PLANO` + `DT_CONTRATACAO`) |
| Sem tabela TREINO_ALTERACAO | Colunas `ID_INSTRUTOR_ALTEROU` e `DT_ALTERACAO` em `TREINO` |
| Sem boleto | `TP_FORMA IN ('PIX','DEBITO','CREDITO')` |

## 6. Perguntas em aberto (não bloqueiam o modelo congelado)

1. Proporção real entre crédito / Pix / débito e taxa de inadimplência mensal.
2. Quantidade de catracas e horários de maior fila.
3. Fluxo exato do aluno TotalPass/Wellhub no cadastro RedFit.
4. Ano civil vs. 12 meses corridos no cálculo da multa do Anual.
5. Quantidade exata de cada aparelho no salão.
