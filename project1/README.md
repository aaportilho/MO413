# Projeto: Estudo Comparativo das Alterações Proteômicas e Funcionais da Placenta em Diabetes, Câncer e Pré-eclâmpsia
# Project: Comparative Study of Proteomic and Functional Changes in the Placenta during Diabetes, Cancer and Pre-eclampsia

## Descrição Resumida do Projeto
### Contexto/Motivação
O projeto visa analisar e comparar alterações proteômicas e funcionais da placenta associadas a diabetes, pré-eclâmpsia e câncer. Essas três doenças são frequentes durante a gestação e acarretam patologias na placenta e consequentemente ao feto.
Portanto o objetivo é investigar como se relacionam os padrões proteômicos e funcionais de placenta de indivíduos com diabetes gestacional, câncer e pré-eclâmpsia.

### Análise
Para desenvolver o projeto serão utilizadas algumas ferramentas, como PubMed e Scorpus para procurar artigos relacionados com o tema; Citoscape e Sting para a construção das redes de interação proteína-proteína;
Reactome para analisar as vias alteradas. Dessa forma, sendo possível constatar que diabetes gestacional, câncer e pré-eclâmpsia podem gerar modulações a nível proteico e funcional semelhantes na placenta.

## Fundamentação Teórica
Os artigos que serão tomados como base para a fundamentação teórica do problema em saúde/biologia:
* Placental structural abnormalities in gestational diabetes and when they develop: A scoping review[^1]
* Fetoplacental oxygen homeostasis in pregnancies with maternal diabetes mellitus and obesity[^2]
* Pre-eclampsia[^3]
* Proteomic Approaches in the Study of Placenta of Pregnancy Complicated by Gestational Diabetes Mellitus[^4]
* Pregnancy and Cancer: Cellular Biology and Mechanisms Affecting the Placenta[^5]

Com foco em investigar como se relacionam os padrões proteômicos e funcionais de placenta de indivíduos com diabetes gestacional, câncer e pré-eclâmpsia.

## Perguntas de Pesquisa
### Pergunta
Como se relacionam os padrões proteômicos e funcionais de placenta de indivíduos com diabetes gestacional, câncer e pré-eclâmpsia?  
### Hipótese
Diabetes gestacional, câncer e pré-eclâmpsia podem gerar modulações a nível proteico e funcional semelhantes na placenta.

## Bases de Dados

> Base de Dados | Endereço na Web | Resumo descritivo
> ----- | ----- | -----
> STRING |[string-db](https://string-db.org/) | Base de dados de interações conhecidas e preditas entre proteínas (PPI). Inclui associações diretas (físicas) e indiretas (funcionais).
> Reactome | [Reactome](https://reactome.org/) | Base de dados contendo conhecimento sobre processos e vias biológicas.
> Scopus | [Scopus](https://www.scopus.com/home.uri) | Repositório para busca de artigos relacionados ao projeto. Tais artigos podem disponibilizar bases de dados usadas posteriormente no projeto.
> PubMed | [PubMed](https://pubmed.ncbi.nlm.nih.gov/) | Repositório de literatura biomédica.

## Modelo Lógico

> Modelo lógico da base de grafos que será construída. Para o modelo de grafos de propriedades, utilize este
> [modelo de base](https://docs.google.com/presentation/d/10RN7bDKUka_Ro2_41WyEE76Wxm4AioiJOrsh6BRY3Kk/edit?usp=sharing) para construir o seu.
> Coloque a imagem do PNG do seu modelo lógico como ilustrado abaixo (a imagem estará na pasta `image`):
>
> ![Modelo Lógico de Grafos](images/modelo-logico-grafos.png)

## Metodologia
> Esta seção evoluirá ao longo do projeto. Nesta primeira entrega, informe técnicas de Ciência de Redes que pretende explorar,
> tais como: detecção de comunidades, análise de centralidade, predição de links, ou a combinação de uma ou mais técnicas. Descreva o que perguntas pretende endereçar cm a técnica escolhida.

## Ferramentas
* PubMed, Scopus --> Busca de artigos
* STRING (string-db) --> Database para redes do tipo Protein-protein Interaction (PPI)
* Reactome --> Database de vias biológicas
* NEO4J, Cytoscape --> Construção e análise das redes PPI

## Referências Bibliográficas

[^1]: Erin Ehlers, Omonseigho O. Talton, Danny J. Schust, Laura C. Schulz,
Placental structural abnormalities in gestational diabetes and when they develop: A scoping review. Placenta, Volume 116, 2021, Pages 58-66. https://doi.org/10.1016/j.placenta.2021.04.005
[^2]: Desoye, G., Carter, A.M. Fetoplacental oxygen homeostasis in pregnancies with maternal diabetes mellitus and obesity. Nat Rev Endocrinol 18, 593–607 (2022). https://doi.org/10.1038/s41574-022-00717-z
[^3]: Dimitriadis, E., Rolnik, D.L., Zhou, W. et al. Pre-eclampsia. Nat Rev Dis Primers 9, 8 (2023). https://doi.org/10.1038/s41572-023-00417-6
[^4]:Lapolla A, Traldi P. Proteomic Approaches in the Study of Placenta of Pregnancy Complicated by Gestational Diabetes Mellitus. Biomedicines. 2022; 10(9):2272. https://doi.org/10.3390/biomedicines10092272
[^5]:Oliveira MdMS, Salgado CdM, Viana LR, Gomes-Marcondes MCC. Pregnancy and Cancer: Cellular Biology and Mechanisms Affecting the Placenta. Cancers. 2021; 13(7):1667. https://doi.org/10.3390/cancers13071667
[^6]: Wolters V, Heimovaara J, Maggen C, et al Management of pregnancy in women with cancerInternational Journal of Gynecologic Cancer 2021;31:314-322. https://doi.org/10.1136/ijgc-2020-001776
