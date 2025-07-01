[![author](https://img.shields.io/badge/author-mateusramos-red.svg)](https://www.linkedin.com/in/mateus-simoes-ramos/) ![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)
# Detecção de Fraudes em Entregas do Walmart

<p align="center">
	<img alt="Capa SQL" width="75%" src="https://github.com/user-attachments/assets/d3f7b7a3-23ca-4005-8d6a-15c3fda5c110">
</p>

<p align="right">
<a href="https://br.freepik.com/vetores-gratis/ilustracao-do-conceito-abstrato-de-armazenamento-de-big-data_12291144.htm#page=2&query=people%20sql&position=0&from_view=search&track=ais&uuid=2f3d7578-d259-48d6-add8-34cc7949006b" >Imagem de vectorjuice
</a> no Freepik
</p>
<br>

## Objetivo do Estudo
 Você é o **analista** de dados do Walmart trabalhando exclusivamente para a área de e-commerce. Foi identificado que o maior aumento proporcional em furtos aconteceu nas compras efetuadas via e-commerce em que usuários relatam não receberem todos os pedidos feitos nas suas compras. Do crescimento de roubos de 2022 para 2023, 53% do aumento veio das compras online. Você foi designado a cuidar deste projeto para diminuir o número de fraudes e roubos, você tem acesso aos dados para poder criar suas hipóteses e recomendações.

## Fonte dos Dados
Os dados estão disponíveis publicamente na plataforma Data World. Abaixo, há um ícone que, ao ser clicado, redireciona para a base de dados. Para acesso no arquivo .ipynb é necessário criar uma chave na plataforma.

## Tecnologias Utilizadas
<p align="left">  
	<a href="https://www.mysql.com/"> <img src="https://github.com/MateusRamos10/SQL_Marketing/assets/43836795/8bfd0366-37bc-4a57-8a2a-f38b380c8ba5" alt="SQL" width="60" height="60"/> 
	</a>
  <a href="https://jupyter.org/" target="_blank" rel="noreferrer"> <img src="https://github.com/MateusRamos10/SQL_Marketing/assets/43836795/50b56155-da53-4c88-9f6b-132edaf99ba2" alt="Jupyter Notebook" width="50" height="50"/> 
	</a>
 	</a>
  <a href="https://data.world/jerrys/introduction-to-data-analytics/workspace/file?filename=orders.csv" target="_blank" rel="noreferrer"> <img src="https://github.com/user-attachments/assets/056316c2-b283-4aca-b90f-8ac9460201ec" alt="Jupyter Notebook" width="50" height="50"/> 
	</a>
</p>


---

<br>
<br>

## Mãos a obra...

> Caso prefira, clique abaixo para pular o desenvolvimento deste trabalho direto para os Resultados.
> <br>
> **[Resultados](#resultados)**

### 1. Entendimento dos Dados
O projeto busca identificar **padrões de fraude em produtos não entregues no Walmart**, especificamente na Flórida central. A análise inicial dos dados revelou um total de 10.000 pedidos, sendo 1.501 com itens faltantes, totalizando um prejuízo de $149.372,61. Foi realizada uma exploração dos dados (df para pedidos com itens faltando, df_original para todos os pedidos), verificando tipos de dados, valores ausentes e estatísticas descritivas.

### 2. Modificação dos Dados
Houve uma etapa de preparação de dados para correção e criação de novos campos. Um exemplo crucial foi a reclassificação das categorias de produtos, onde foi utilizado o Gemini para corrigir inconsistências, como cereais categorizados incorretamente como "Cuidado Pessoal".

### 3. Identificação de Padrões
A matriz de correlação de Pearson mostrou baixa significância entre as variáveis, com a maior correlação (0.13) entre items_missing e order_amount. Dessa forma, o foco da análise de padrões se deslocou para uma abordagem temporal. Foi criada uma coluna hour para a delivery_hour e observado que as maiores taxas de fraude ocorrem às 22h (19%) e às 6h (18%). A análise por data não revelou padrões sazonais significativos próximos a feriados. A investigação de produtos e categorias com itens faltantes apontou que as categorias "Pantry" (alimentos não perecíveis) e "Electronics" são as mais afetadas. Em relação aos entregadores, foi notado que os com idade entre 18 e 22 anos são responsáveis por 20% das fraudes e que a reincidência de 3 a 4 ocorrências é comum entre os envolvidos.

### 4. Avaliação de Causas
A avaliação das causas, baseada nas análises, permitiu identificar tendências importantes:

- Correlação: A baixa correlação entre as variáveis indica que a fraude não está ligada a fatores simples e isolados.
- Horário: Os picos de fraude nas primeiras horas da manhã (6h) e no final da noite (22h) sugerem que a visibilidade ou supervisão podem ser fatores.
- Sazonalidade: Não há indícios de que feriados impactem diretamente o índice de fraude.
- Itens/Categorias: A disparidade nas categorias "Pantry" e "Electronics" exige abordagens distintas devido ao valor agregado dos produtos.
- Entregadores: A idade e a reincidência de entregadores apontam para a necessidade de políticas mais rigorosas.

### 5. Identificação de Padrões
 Este problema multifacetado, com possíveis causas no entregador, no cliente ou em falhas de sistema, exige uma abordagem com recomendações claras para mitigação, foram exploradas várias direçoes, algumas relevantes e outras não relevantes.

- Análise Temporal por Hora de Entrega
- Análise Temporal por Mês
- Análise por Produto
- Análise por Categoria
- Análise por Preço
- Análise por Valor Total da Ordem
- Análise por Região
- Análise por Quantidade de Itens Entregues na Ordem
- Análise por Entregadores
- Análise por Clientes
- Análise por Idade dos Entregadores
- Análise por Quantidade de Entregas (Trips) dos Entregadores

<br>
<br>
<br>

## Resultados <a id="resultados"></a>

Os resultados das análises indicam que as fraudes em produtos não entregues no Walmart central da Flórida não seguem um padrão simples de correlação linear com as variáveis disponíveis. No entanto, foram identificadas tendências claras: os horários de entrega entre 22h e 6h apresentam as maiores taxas de fraude. As categorias "Pantry" (alimentos não perecíveis) e "Electronics" são as mais afetadas, exigindo estratégias de mitigação diferenciadas. Além disso, entregadores mais jovens (18 a 22 anos) e aqueles com múltiplas reincidências (3 a 4 ocorrências) são consistentemente associados a incidentes de fraude. Estas observações sugerem que a responsabilidade pela fraude pode ser multifatorial, envolvendo tanto falhas operacionais quanto condutas inadequadas de entregadores ou clientes.
