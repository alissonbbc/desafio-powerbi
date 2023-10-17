# desafio-powerbi
_Desafio 2 de Power BI do bootcamp DIO (transformação de dados), trilha de ciência de dados._

## Etapas prévias
1. Criada instância na Azure para MySQL.
2. Banco de dados inserido na Azure via Cloud Shell (arquivo sql disponível no diretório)

## Edição de dados via Power Query
1. Cabeçalhos verificados.
2. Tipo das variáveis employee.Ssn, employee.Super_ssn, works_on.Essn, dependent.Essn, department.Mgr_ssn alterado para número inteiro.
3. Tipo monetário alterado para decimal fixo em employee.Salary.
4. Employee com Super_ssn nulo, 'James E. Borg', de Ssn '888665555', é gerente de outros dois gerentes e ocupa, portanto, o cargo mais alto da hierarquia listado no banco de dados.
5. Verificou-se que não há departamentos sem gerentes.
6. Nota-se que há registro de 0 horas para o Essn '888665555' no projeto de Pno 20. O valor não será editado por entender-se que pode não haver inciado o trabalho do gerente (geral) neste projeto.
7. Coluna Address dividida duas vezes, por delimitador '-' mais à esquerda e depois mais à direita, para separar número, logradouro e Estado. Colunas renomeadas de acordo com conteúdos.
8. Feita mescla via Power Query da consulta employee (base) com a consulta departamentos, de tipo externa esquerda. As colunas desnecessárias foram removidas.
9. Colunas de nome e sobrenome mescladas na nova tabela de employee.
10. Criada na tabela employee nova uma coluna via Power Query com nome do gerente de acordo com o Mgr_ssn.
11. Removidas duas últimas linhas (duplicadas) da tabela dept_locations para mescla com department.
12. Mescla de department (base) com dept_locations, externa esquerda. Foi utilizada criação com exemplo baseado no código do gerente, dado que não havia tabela específica para gerentes e criá-la incorreria em maior dispêndio de recursos.
13. Dados agrupados para indicar número de subordinados a cada gerente.
14. Eliminadas todas colunas desnecessárias.
15. Transformações aplicadas
16. Atualizados os relacionamentos para construção do relatório.
17. Construção do relatório.