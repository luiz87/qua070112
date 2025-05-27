## 01. function idade
Implemente uma função no MySQL chamada idade que recebe como entrada um valor do tipo DATE e retorne a idade atual dessa data como tipo INT.
- A função deve ser not determinística, pois cada execução pode gerar um valor diferente, seguido de reads sql data.
- Utilize a função interna CURDATE() ou NOW() do MySQL para obter a data atual.

```sql
select idade('1987-07-21');
-- 37
```

## 02. function faixa_etaria
Implemente uma função no MySQL chamada faixa_etaria que recebe como entrada um valor do tipo DATE e retorne a faixa etária em VARCHAR.
- A função deve ser not determinística, pois cada execução pode gerar um valor diferente, seguido de reads sql data.
- Utilize a função idade() para obter a idade atual.
- Utilize o calculo com div para facilitar a implementação.
- As faixas etárias devem ser sempre ser entre *0 e *9 Exemplos:
  - A idade 08 deve ficar Entre 00 e 09 anos.
  - A idade 26 deve ficar Entre 20 e 29 anos.
  - A idade 41 deve ficar Entre 40 e 49 anos.

```sql
select faixa_etaria('1987-07-21');
-- Entre 30 e 40 anos
```

## 03. procedure atualizar_gol_partida
Crie uma Stored Procedure chamada atualizar_gol_partida que preencha os campos de gols na tabela partida. A procedure deve:
- Receber a sigla dos times mandates e visitantes
- Receber o número de gols do mandante e visitante
  - Para teste limpe antes os resultados da rodada 38

```sql
update partida set gol_mandante = null, gol_visitante = null where rodada = 38;
-- RODADA 38
CALL atualizar_gol_partida('GRE',0,3,'COR');
CALL atualizar_gol_partida('CAM',1,0,'CAP');
CALL atualizar_gol_partida('BAH',2,0,'ACG');
CALL atualizar_gol_partida('FLA',2,2,'VIT');
CALL atualizar_gol_partida('BOT',2,1,'SAO');
CALL atualizar_gol_partida('PAL',0,1,'FLU');
CALL atualizar_gol_partida('RBB',5,1,'CRI');
CALL atualizar_gol_partida('FOR',3,0,'INT');
CALL atualizar_gol_partida('CUI',1,2,'VAS');
CALL atualizar_gol_partida('JUV',0,1,'CRU');
```

## 04. procedure gerar_resultado_aleatorio
Crie uma Stored Procedure chamada gerar_resultado_aleatorio que preencha aleatoriamente os campos de gols em uma tabela chamada partida. A procedure deve:

- Iterar por todos os registros da tabela partida, utilizando um contador para identificar o campo id_partida.
- Gerar valores aleatórios para os campos:
  - gol_mandante: Um número inteiro aleatório entre 0 e 6.
  - gol_visitante: Um número inteiro aleatório entre 0 e 6.
- Atualizar os valores gerados para cada registro identificado pelo id_partida.
- Parar a execução ao atingir o último registro (ou quando o contador chegar a 380, que representa o número total de partidas no contexto fornecido).

```sql
call gerar_resultado_aleatorio();
select * from classificacao;
```
