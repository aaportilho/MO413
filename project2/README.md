# Projeto: Estudo Comparativo das Alterações Proteômicas e Funcionais da Placenta em Diabetes, Câncer e Pré-eclâmpsia
# Project: Comparative Study of Proteomic and Functional Changes in the Placenta during Diabetes, Cancer and Pre-eclampsia

## Descrição Resumida do Projeto
### Contexto/Motivação
O projeto visa analisar comparativamente as alterações proteômicas e funcionais da placenta associadas à pré-eclâmpsia e ao câncer. Essas duas doenças são frequentes durante a gestação e acarretam patologias na placenta e, consequentemente, ao feto. Portanto, investigar como as proteínas na placenta de gestantes com cânces ou pré-eclâmpsia foram reguladas, a interação entre essas proteínas, e as vias biológicas influenciadas, pode revelar padrões proteômicos e funcionais que auxiliem no entendimento e tratamento de ambas doenças.

### Análise
Para o desenvolvimento deste projeto serão utilizadas diferentes ferramentas, tais como PubMed e Scorpus para procurar artigos relacionados com o tema; Cytoscape e Sting para a construção das redes de interação proteína-proteína; Reactome para analisar as vias biológicas alteradas. Por meio dessa análise, será possível verificar que câncer e pré-eclâmpsia podem gerar modulações a nível proteico e funcional semelhantes na placenta.

## Slides
[Apresentação Projeto P2](assets/slides/apresentacao_projeto_p2.pdf)

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

## Metodologia
O projeto pretende explorar o problema seguindo a seguinte metodologia:
1. Seleção dos artigos relevantes com foco em estudos pré-clínico em placenta com análises proteômicas (critério de inclusão);
2. Fazer uma curadoria dos dados da proteômica, selecionando as proteínas alteradas a serem estudadas;
3. Filtrar proteínas em relação ao grau de expressão e separá-las pelas que apresentam maior ou menor expressão;
4. Construir e analisar as redes de interação proteína-proteína para cada doença. em seguida, integrar as redes de ambas doenças e analisar as proteínas em comum;
* Utilizar técnicas exploratórias de ciência de redes, tais como: análise de centralidade para identificar proteínas mais relevantes que são afetadas pelas doenças; identificação de comunidades de proteínas que podem se repetir entre as diferentes doenças.
5. Aplicar métodos de análise de enriquecimento de vias para contruir uma rede de associação entre vias biológicas e as proteínas alteradas. Utilizar a rede resultante para identificar os principais mecanismos biológicos associados às duas doenças.

## Bases de Dados e Evolução
> Base de Dados | Endereço na Web | Resumo descritivo
> ----- | ----- | -----
> STRING |[string-db](https://string-db.org/) | Base de dados de interações conhecidas e preditas entre proteínas (PPI). Inclui associações diretas (físicas) e indiretas (funcionais).
> Reactome | [Reactome](https://reactome.org/) | Base de dados contendo conhecimento sobre processos e vias biológicas.
> Scopus | [Scopus](https://www.scopus.com/home.uri) | Repositório para busca de artigos relacionados ao projeto. Tais artigos podem disponibilizar bases de dados usadas posteriormente no projeto.
> PubMed | [PubMed](https://pubmed.ncbi.nlm.nih.gov/) | Repositório de literatura biomédica.

## Modelo Lógico
![Modelo Lógico de Grafos](assets/images/modelo-logico-grafos.png)

## Integração entre Bases

## Análise Preliminar
Até o momento, o foco do projeto foi realizar o tratamento dos dados e a construção das redes de proteínas para cada doença, assim como a integração de ambas.
Dadas as propriedades escolhidas no STRING para definir a interação entre as proteínas, notamos que na rede de câncer cerca de 111 proteínas estão interligadas. Já na pré-eclâmpsia, foi visto que 103 proteínas possuem interação.
Após integrar as duas redes, foi observado que apenas 12 proteínas estão em comum, sendo 5 delas com a mesma regulação (up ou down). Dessas proteínas, duas estão up regulated: Alfa-actinina-1 e Hemopexina. E três estão down regulated: Subunidade beta do complexo AP-2, Inibidor de apoptose 5, Cadeia de tubulina beta-3.

## Evolução do Projeto
Inicialmente, o projeto tinha como proposta analisar os padrões proteômicos na placenta de ratas, relacionados a três patologias: Diabetes, Câncer e Pré-eclâmpsia. Contudo, durante a revisão da literatura, não foram encontrados resultados relevantes para a diabetes. Diante disso, decidimos prosseguir com o estudo focado nas outras duas doenças.

Além disso, após o feedback da primeira entrega, foram realizadas modificações no modelo lógico. Durante o desenvolvimento, aumentamos a compreensão do projeto e modificamos o modelo lógico para de fato refletir as redes de interação entre proteínas, os atributos que iriam caracterizar cada nó, e a interação dessas proteínas com vias biológicas associadas.

Durante esse primeiro mês de elaboração do projeto foi realizado o levantamento bibliográfico nas bases do PubMed e do Scorpus. Os dados adquiridos foram tabulados no Excel. Com auxílio do Python, realizou-se a curadoria dos dados e sua inserção no STRING para a elaboração de redes de interação proteína-proteína. A rede gerada utilizava os nomes de proteína (uniprot), porém os nós recebiam a denominação do gene.

Os resultados dessa rede de interação foram inseridos no Cytoscape, após o processamento dos dados em Python e integração das redes e dos atributos dos nós no Neo4j. No Cytoscape os títulos dos nós foram alterados para os nomes de proteína. Além disso, foram analisadas as redes associadas para facilitar a verificação de proteínas em comum das duas redes.

Os próximos passos serão analisar os atributos dos nós (regulação up ou down, fold change) das redes e analisar a topologia de rede (centralidade e comunidade) no Cytoscape. Além disso, será realizado o enriquecimento da rede buscando por vias biológicas relacionadas, utilizando o Reactome. Com esses resultados será possível identificar os padrões mais relevantes e, por fim, realizar a interpretação biológica dos achados.

## Ferramentas
Para o levantamento bibliográfico e definição das proteínas reguladas nas doenças, foram utilizadas as bases de dados PubMed e Scorpus. 
Os dados adquiridos foram tabulados no Excel. Com auxílio do Python, realizou-se a curadoria dos dados e sua inserção no STRING (string-db). 
O STRING é um banco de dados biológicos que auxilia na elaboração de redes de interação proteína-proteína. Essas redes de interações entre proteínas foram processadas utilizando Python e Neo4j para integração e criação dos atributos dos nós (Neo4J é um sistema de gerenciamento de banco de dados gráfico).Posteriormente, as redes foram inseridas no Cytoscape para análises específicas.
No Cytoscape é possível fazer o enriquecimento dos grafos separadamente e associados.
Após a identificação das proteínas que exercem maior influência na placenta no câncer e/ou na pré-eclâmpsia, será utilizado o Reactome. Este é um banco de dados biológicos que permite visualizar as vias biológicas alteradas a partir de genes ou proteínas.

TL;DR:
* PubMed, Scopus --> Busca de artigos
* STRING (string-db) --> Database para redes do tipo Protein-protein Interaction (PPI)
* Reactome --> Database de vias biológicas
* Python, NEO4J, Cytoscape --> Construção, integração e análise das redes PPI

## Referências Bibliográficas
[^1]: Erin Ehlers, Omonseigho O. Talton, Danny J. Schust, Laura C. Schulz,
Placental structural abnormalities in gestational diabetes and when they develop: A scoping review. Placenta, Volume 116, 2021, Pages 58-66. https://doi.org/10.1016/j.placenta.2021.04.005
[^2]: Desoye, G., Carter, A.M. Fetoplacental oxygen homeostasis in pregnancies with maternal diabetes mellitus and obesity. Nat Rev Endocrinol 18, 593–607 (2022). https://doi.org/10.1038/s41574-022-00717-z
[^3]: Dimitriadis, E., Rolnik, D.L., Zhou, W. et al. Pre-eclampsia. Nat Rev Dis Primers 9, 8 (2023). https://doi.org/10.1038/s41572-023-00417-6
[^4]:Lapolla A, Traldi P. Proteomic Approaches in the Study of Placenta of Pregnancy Complicated by Gestational Diabetes Mellitus. Biomedicines. 2022; 10(9):2272. https://doi.org/10.3390/biomedicines10092272
[^5]:Oliveira MdMS, Salgado CdM, Viana LR, Gomes-Marcondes MCC. Pregnancy and Cancer: Cellular Biology and Mechanisms Affecting the Placenta. Cancers. 2021; 13(7):1667. https://doi.org/10.3390/cancers13071667
[^6]: Wolters V, Heimovaara J, Maggen C, et al Management of pregnancy in women with cancer International Journal of Gynecologic Cancer 2021;31:314-322. https://doi.org/10.1136/ijgc-2020-001776
