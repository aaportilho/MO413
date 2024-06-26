# Projeto: Estudo Comparativo das Alterações Proteômicas e Funcionais da Placenta em Diabetes, Câncer e Pré-eclâmpsia
# Project: Comparative Study of Proteomic and Functional Changes in the Placenta during Diabetes, Cancer and Pre-eclampsia

## Descrição Resumida do Projeto
## Contexto/Motivação
O projeto tem como objetivo realizar uma análise comparativa das alterações proteômicas e funcionais da placenta associadas à pré-eclâmpsia e ao câncer. Ambas as condições são frequentes durante a gestação e podem resultar em complicações placentárias significativas, afetando diretamente o desenvolvimento fetal. Investigar as modulações das proteínas na placenta de gestantes com câncer ou pré-eclâmpsia, bem como suas interações e o impacto nas vias biológicas, pode revelar padrões proteômicos e funcionais essenciais para o entendimento e tratamento dessas doenças.

## Análise/Resultados 
Para alcançar esse objetivo, serão utilizadas diversas ferramentas, como PubMed e Scopus para revisão bibliográfica, STRING para construção de redes de interação proteína-proteína, Python para integração e validação dos dados, KEGG para análise das vias biológicas afetadas, e Cytoscape para a visualização e análise das redes complexas geradas. Os resultados obtidos indicam que essas condições compartilham alterações similares em termos de proteínas e vias funcionais no tecido placentário. No entanto, dada a natureza abrangente das análises ômicas, será crucial realizar análises adicionais para aprofundar o estudo das vias por meio de expressão gênica e proteica.


## Slides
[Apresentação Projeto P3](assets/slides/apresentacao_projeto_p3.pdf)

## Fundamentação Teórica
Os artigos que serão tomados como base para a fundamentação teórica do problema em saúde/biologia:
* Placental structural abnormalities in gestational diabetes and when they develop: A scoping review[^1]
* Fetoplacental oxygen homeostasis in pregnancies with maternal diabetes mellitus and obesity[^2]
* Pre-eclampsia[^3]
* Proteomic Approaches in the Study of Placenta of Pregnancy Complicated by Gestational Diabetes Mellitus[^4]
* Pregnancy and Cancer: Cellular Biology and Mechanisms Affecting the Placenta[^5]
* Management of pregnancy in women with cancer[^6]

O foco da pesquisa nesses artigos é investigar as alterações em padrões proteômicos e funcionais de placenta de indivíduos com câncer e pré-eclâmpsia.

## Perguntas de Pesquisa
### Pergunta
Como se relacionam os padrões proteômicos e funcionais de placenta de indivíduos com câncer e pré-eclâmpsia?  
### Hipótese
Câncer e pré-eclâmpsia podem gerar modulações a nível proteico e funcional semelhantes na placenta.

O projeto de pesquisa ajudou a analisar as modulações proteicas nas duas condições: câncer e pré-eclâmpsia. Foi possível verificar se nessas circunstâncias existiam alterações proteômicas e das vias biológicas de forma similar para ambas doenças no tecido placentário. Além disso, conseguimos identificar o sentido da regulação dessas vias em cada doença dada a informação das proteínas relacionadas.

## Metodologia
O projeto pretende explorar o problema seguindo a seguinte metodologia:
1. Seleção dos artigos relevantes com foco em estudos pré-clínico em placenta com análises proteômicas (critério de inclusão de proteínas e vias biológicas);
2. Curadoria dos dados da proteômica, selecionando as proteínas alteradas a serem estudadas;
3. Filtragem de proteínas em relação ao grau de expressão, separando as que apresentam maior ou menor expressão diferencial;
4. Construção e análise das redes de interação proteína-proteína para cada doença;
5. Integração das redes de ambas doenças e análise das proteínas em comum;
* Utilizar técnicas exploratórias de ciência de redes, tais como: análise de centralidade para identificar proteínas mais relevantes que são afetadas pelas doenças e se elas se mantêm centrais em ambas as redes; 
5. Aplicação de métodos de análise de enriquecimento com vias biológicas, construindo a rede heterogênea de associação entre as vias e as proteínas alteradas. 
6. Integração das redes enriquecidas de cada doença de forma a gerar uma rede com as vias biológicas em comum.
* Utilização da rede resultante para identificar os principais mecanismos biológicos associados às duas doenças. Identificação de comunidades que podem ser similares entre as diferentes doenças.


## Bases de Dados e Evolução
> Base de Dados | Endereço na Web | Resumo descritivo
> ----- | ----- | -----
> STRING |[string-db](https://string-db.org/) | Base de dados de interações conhecidas e preditas entre proteínas (PPI). Inclui associações diretas (físicas) e indiretas (funcionais).
> KEGG | [Kegg](https://www.genome.jp/kegg/) | B Base de dados contendo conhecimento sobre redes de interação molecular nas células e variantes específicas a determinado organismo.
> Scopus | [Scopus](https://www.scopus.com/home.uri) | Repositório para busca de artigos relacionados ao projeto. Tais artigos podem disponibilizar bases de dados usadas posteriormente no projeto.
> PubMed | [PubMed](https://pubmed.ncbi.nlm.nih.gov/) | Repositório de literatura biomédica.

Os dados de proteínas alteradas que foram extraídos de artigos do Scopus/PubMed e do projeto do  foram tratados para serem compatíveis com o STRING e gerar as redes de interação. Assim, foi necessário mapear os identificadores de proteínas utilizados pelos artigos (UNIPROT) para os genes referentes, uma vez que o STRING utiliza o nome do gene como identificador dos nós das redes.
Além disso, algumas proteínas possuíam vários sinônimos separados por ponto e vírgula, dos quais selecionamos um que fosse reconhecido pelo UNIPROT e STRING. Por fim, foram removidas proteínas não identificadas em nenhuma das bases.
Em relação às redes com as vias biológicas do Kegg, foi necessário tratar a tabela extraída para uma formatação que representasse as arestas da rede, uma vez que a formatação original indicava as proteínas em um formato de lista referente a cada via.


## Modelo Lógico
![Modelo Lógico de Grafos](assets/images/modelo-logico-grafos.png)

## Integração entre Bases
A princípio, as bases para cada uma das duas doenças estudadas foram armazenadas em abas de um arquivo excel. Esse arquivo possui informações como: o identificador das proteínas alteradas, o gene relacionado, o fold change e o tipo de regulação (up/down).

Estes dados foram processados de maneira a remover dados duplicados, padronizar os nomes das colunas e juntar as informações quando a mesma proteína estava presente em ambas doenças através de um script em Python.

Após inserir as proteínas de cada doença na base do STRING e extrair as redes de interação (PPI), foi necessário associar as informações de regulação das proteínas (fold change e tipo de regulação) aos atributos dos nós dessas redes por meio do NEO4J.

Dessa forma, conseguimos gerar uma rede final que representava a interação das proteínas alteradas em ambas doenças e os atributos advindos da regulação em cada doença específica.
Por fim, utilizando as proteínas presentes nas redes PPI geradas pelo STRING, foi necessário realizar o enriquecimento com vias biológicas do KEGG. Após processar as tabelas extraídas do KEGG, é possível construir as redes heterogêneas de interação de proteínas com as vias e analisar, por exemplo, as vias em comum de ambas doenças.

Em todas as etapas, houveram perdas de algumas proteínas devido a falta de relacionamentos encontrados nas bases de dados. O seguinte diagrama representa o fluxo desses dados:

![Fluxo dos dados](assets/images/diagram_data_flow.png)
*Figura 1. Diagrama do fluxo de dados na integração entre as bases.*


## Análises Realizadas


## Evolução do Projeto
Inicialmente, o projeto tinha como proposta analisar os padrões proteômicos na placenta de ratas, relacionados a três patologias: Diabetes, Câncer e Pré-eclâmpsia. Contudo, durante a revisão da literatura, não foram encontrados resultados relevantes para a diabetes. Diante disso, decidimos prosseguir com o estudo focado nas outras duas doenças.

Além disso, após o feedback da primeira entrega, foram realizadas modificações no modelo lógico. Durante o desenvolvimento, aumentamos a compreensão do projeto e modificamos o modelo lógico para de fato refletir as redes de interação entre proteínas, os atributos que iriam caracterizar cada nó, e a 
interação dessas proteínas com vias biológicas associadas.

Durante o primeiro mês de elaboração do projeto foi realizado o levantamento bibliográfico nas bases do PubMed e do Scorpus. Os dados adquiridos foram tabulados no Excel. Com auxílio do Python, realizou-se a curadoria dos dados e sua inserção no STRING para a elaboração de redes de interação proteína-proteína. A rede gerada utilizava os nomes de proteína (uniprot), porém os nós recebiam a denominação do gene.

Os resultados dessa rede de interação foram inseridos no Cytoscape, após o processamento dos dados em Python e integração das redes e dos atributos dos nós no Neo4j. No Cytoscape os títulos dos nós iam ser alterados para os nomes de proteína, porém após um levantamento de artigos, foi certificado que utilizar o nome do gene era o mais usual. Além disso, foram analisadas as redes associadas para facilitar a verificação de proteínas/genes em comum das duas redes.

Após isso, foram analisados os atributos dos nós (regulação up ou down, fold change) das redes e analisar a topologia de rede (centralidade e comunidade) no Cytoscape. Além disso, foi realizado o enriquecimento da rede buscando por vias biológicas relacionadas, utilizando o Kegg. Com esses resultados foi possível identificar os padrões mais relevantes e, por fim, realizar a interpretação biológica dos achados e a discussão com a literatura.


## Ferramentas
Para o levantamento bibliográfico e definição das proteínas reguladas nas doenças, foram utilizadas as bases de dados PubMed e Scorpus. 
Os dados adquiridos foram tabulados no Excel. Com auxílio do Python, realizou-se a curadoria dos dados e sua inserção no STRING (string-db). 
O STRING é um banco de dados biológicos que auxilia na elaboração de redes de interação proteína-proteína. Essas redes de interações entre proteínas foram processadas utilizando Python e Neo4j para integração e criação dos atributos dos nós (Neo4J é um sistema de gerenciamento de banco de dados gráfico).Posteriormente, as redes foram inseridas no Cytoscape para análises específicas.
No Cytoscape é possível fazer o enriquecimento dos grafos separadamente e associados.
Após a identificação das proteínas que exercem maior influência na placenta no câncer e/ou na pré-eclâmpsia, será utilizado o Reactome. Este é um banco de dados biológicos que permite visualizar as vias biológicas alteradas a partir de genes ou proteínas.

TL;DR:
* PubMed, Scopus --> Revisão bibliográfica e busca por proteínas alteradas
* STRING (string-db) --> Database para redes do tipo Protein-protein Interaction (PPI)
* Reactome --> Database de vias biológicas
* Python, NEO4J, Cytoscape --> Construção, integração e análise das redes PPI

## Resultados/Discussão

## Conclusão

## Trabalhos Futuros

## Referências Bibliográficas
[^1]: Alberts B, Johnson A, Lewis J, et al. Molecular Biology of the Cell. 4th edition. New York: Garland Science; 2002. The Endoplasmic Reticulum. Available from: https://www.ncbi.nlm.nih.gov/books/NBK26841/

[^2]: Almanza A, Carlesso A, Chintha C, Creedican S, Doultsinos D, Leuzzi B, Luís A, McCarthy N, Montibeller L, More S, Papaioannou A, Püschel F, Sassano ML, Skoko J, Agostinis P, de Belleroche J, Eriksson LA, Fulda S, Gorman AM, Healy S, Kozlov A, Muñoz-Pinedo C, Rehm M, Chevet E, Samali A. Endoplasmic reticulum stress signalling - from basic mechanisms to clinical applications. FEBS J. 2019 Jan;286(2):241-278. doi: 10.1111/febs.14608. 

[^3]: Aye ILMH, Aiken CE, Charnock-Jones DS, Smith GCS. Placental energy metabolism in health and disease-significance of development and implications for preeclampsia. Am J Obstet Gynecol. 2022 Feb;226(2S):S928-S944. doi: 10.1016/j.ajog.2020.11.005. Epub 2020 Nov 13. 

[^4]: Camargo, E.B., Moraes, L.F.S., Souza, C.M. et al. Survey of calcium supplementation to prevent preeclampsia: the gap between evidence and practice in Brazil. BMC Pregnancy Childbirth 13, 206 (2013). https://doi.org/10.1186/1471-2393-13-206

[^5]: Dai, W., Pollinzi, A.; Piquette-Miller, M. Use of Traditional and Proteomic Methods in the Assessment of a Preclinical Model of Preeclampsia. Drug Metab Dispos 51:1308–1315 (2023). https://dx.doi.org/10.1124/dmd.122.001080.

[^6]: Dimitriadis, E., Rolnik, D.L., Zhou, W. et al. Pre-eclampsia. Nat Rev Dis Primers 9, 8 (2023). https://doi.org/10.1038/s41572-023-00417-6

[^7]: Ferreira da Silva RC, Malhão TA, Rezende LFM, da Silva Barbosa R, Correa Schilithz AO, et al. Current and future costs of cancer attributable to insufficient leisure-time physical activity in Brazil. PLOS ONE 18(10): e0293771. (2023). https://doi.org/10.1371/journal.pone.0287224

[^8]: Iwawaki T, Akai R, Yamanaka S, Kohno K. Function of IRE1 alpha in the placenta is essential for placental development and embryonic viability. Proc Natl Acad Sci U S A. 2009 Sep 29;106(39):16657-62. doi: 10.1073/pnas.0903775106. Epub 2009 Sep 15. PMID: 19805353; PMCID: PMC2757843.

[^9]: Oliveira MdMS, Salgado CdM, Viana LR, Gomes-Marcondes MCC. Pregnancy and Cancer: Cellular Biology and Mechanisms Affecting the Placenta. Cancers. 2021; 13(7):1667.

[^10]: Rabinowitz JD, Enerbäck S. Lactate: the ugly duckling of energy metabolism. Nat Metab. 2020 Jul;2(7):566-571. doi: 10.1038/s42255-020-0243-4. Epub 2020 Jul 20. PMID: 32694798; PMCID: PMC7983055.

[^11]: Sun R, Yang L, Wang Y, Zhang Y, Ke J, Zhao D. DNAJB11 predicts a poor prognosis and is associated with immune infiltration in thyroid carcinoma: a bioinformatics analysis. J Int Med Res. 2021 Nov;49(11):3000605211053722. doi: 10.1177/03000605211053722. 

[^12]: Wolters V, Heimovaara J, Maggen C, et al Management of pregnancy in women with cancer International Journal of Gynecologic Cancer 2021;31:314-322. https://doi.org/10.1136/ijgc-2020-001776


