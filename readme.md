<!-- antes de enviar a versão final, solicitamos que todos os comentários, colocados para orientação ao aluno, sejam removidos do arquivo -->
# Aplicações de Otimização para Lançamento de Novos Produtos

#### Aluno: [Victor Soledade Moraes Amaral Neto](https://github.com/link_do_github)
#### Orientador: [Ana Carolina Abreu](https://github.com/link_do_github).
#### Co-orientador: [Felipe Borges](https://github.com/link_do_github). <!-- caso não aplicável, remover esta linha -->

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

<!-- para os links a seguir, caso os arquivos estejam no mesmo repositório que este README, não há necessidade de incluir o link completo: basta incluir o nome do arquivo, com extensão, que o GitHub completa o link corretamente -->
- [Link para o código](https://github.com/VictorAmaralNeto/TCC-BI-Master-Victor-Amaral/blob/main/Arquivo%20da%20Modelagem.xlsm)

- Trabalhos relacionados: <!-- caso não aplicável, remover estas linhas -->
    - [Análise de Agrupamentos com Uso do Excel - Oliveira (2015)](https://repositorio.ufmg.br/bitstream/1843/BUBD-A3QEUR/1/monografia_davidson_vers_o_final.pdf).
    - [The Impact of Price Segmentation based on Customer Characteristics, Product Bundle or Product Features on Price Fairness Perceptions - Nazari e Sheikholeslami-2021](https://jimm.journals.umz.ac.ir/article_3367_e408bef6742b349b39977526f3746607.pdf).
    - [A optimal pricing and quantity of products with two offerings - Khouja e Robbins (2003)](http://gauss.stat.su.se/gu/sg/2012VT/deluppgift23.pdf).
    - [Application of the Price Discrimination in Marketing - Porcheva (2013)](https://www.researchgate.net/profile/Tatyana-Netseva-Porcheva/publication/341452650_Application_of_the_Price_Discrimination_in_Marketing/links/5ec2311d92851c11a87043ce/Application-of-the-Price-Discrimination-in-Marketing.pdf).
  
---

### Resumo

Este trabalho procurou dar contribuição aos empreendedores ou aos candidatos a ter um novo negócio de melhoria de seu processo decisório com os objetivos de reduzir o risco ou aumentar o potencial de resultado de seus novos produtos aplicando algoritmos de otimização.
As abordagens aqui aplicadas implicaram: 1) utilização de otimização por algoritmo genético para buscar em uma pesquisa de mercado com 50 respondentes possíveis segmentos de mercado que, além das características sociodemográficas, considerassem preço máximo que o indivíduo pagaria pelo produto (WTP: Willingness to Pay); 2) aplicação de Simulação de Monte Carlo com otimização para definição de preço ótimo para os segmentos de maior potencial de lucratividade identificados na etapa anterior. A ferramenta utilizada foi Excel/Solver. Desta forma, espera-se que este trabalho possa ter utilidade mais abrangente tendo em vista o alcance de uso deste software, que está ao alcance de qualquer interessado nestas aplicações.
Nesta abordagem pode-se confirmar que a aplicação das técnicas de otimização propiciou encontrar segmentos distintos na base de dados e propiciou também contribuir para com as decisões de precificação e alocação de verba de divulgação para atingir, dependendo da intenção do empreendedor, diferentes objetivos: otimização do lucro, minimização do risco ou ainda melhor relação retorno risco. A aplicação de modelos de otimização resultou em estabelecimento dos 3 parâmetros de decisão (Escolha dos segmentos de mercado, definição dos preços para cada segmento e alocação de verba de divulgação a cada segmento escolhido) materialmente melhores do que modo prevalente no mercado de lançar os produtos para diversos perfis de consumidores ao preço similar ao de produtos similares.

### 1. Introdução

O empreendedorismo, além de seu reconhecido valor para a Economia, vem se tornando necessidade de muitos indivíduos que não conseguem oportunidades no mercado formal de trabalho. Por outro lado, a taxa de insucesso dos novos negócios pode impactar materialmente todos os envolvidos (proprietário, empregdos, fornecedores entre outros) Neste contexto, utilizando pesquisa de mercado de novo e-book, procurou-se demonstrar como algoritmos de otimização conjugados com técnicas de decisão sob inceteza podem melhorar decisões complexas de mercado, tais como:

  - Qual ou quais preços devem ser cobrados pelo produto de acordo com diferentes objetivos?
  - Qual ou quais segmentos de mercado devem ser acionados?
  - Qual é a lucratividade esperada do projeto?
  - Quais são os riscos de perda e qual é a probabilidade de que ocorra?

Portanto, esta abordagem procurou lançar luz, através de modelagem matemática, em tês perguntas principais:

  - 1) A segumentação de mercado com decorrente possibilidade de cobrar preços diferentes para cada um deles potencializa a relação retorno/risco do produto?
  - 2) A prática de otimização de preços (precificação estratégica) potencializa a relação retorno/risco do produto?
  - 3) Em que medida a aplicação de otimização sob incerteza contribui para que decisões mais assertivas sejam tomadas?  

Para alcançar estas intenções, lançou-se mão de matérias pertencentes às áreas de Microeconomia, Estatística, Machine Learning e Marketing. Elas foram aplicadas a uma pesquisa de mercado feita com cinquenta respondentes em que se procurou medir a aceitação de um e-book e, mais importante, medir o valor máximo que cada um deles estaria disposto a pagar.

Embora se reconheça a imprescindível necessidade de se contar com a sensibilidade do especialista, as técnicas quantitativas possibilitaram melhorar decisões, minimizando a chance de haver prejuízos ou, na melhor das hipóteses, de haver lucros sub ótimos em um projeto de lançamento de um novo produto.

Apesar das limitações nesta abordagem (base reduzida, base desbalanceada e vieses de conveniência social), foi possível verificar o valor das modelagens matemáticas com complemento à experiência e intuição humanas.

Como tentativa de democratizar a aplicação da abordagem deste trabalho para pequenos empreendedores, toda a modelagem foi desenvolvida em Excel, tornando desnecessária qualquer programação em outras ferramentas, mas tão somente conhecimento avançado nesta software.


### 2. Modelagem

A modelagem do trabalho contou com três dimensões. 1) segmentação da base de dados utilizando técnica de agrupamento, aplicando Excel/Solver/Evolutinary; 2) Cálculo das curvas de demanda da base completa e dos dois segmentos mais promissores e 3) aplicação de otimização com Simulação de Monte Carlo para definir preços ótimos e verbas de divulgação para atender aos objetivos de maximizar lucro ou minimizar riscos ou de encontrar relação ótima risco/retorno.

Segmentação de Mercado

Como mencionado, a modelagem foi integralmente feita em Excel. Seguiu as seguintes etapas:

  - Análise exploratória da base de dados (50 respostas da pesquisa);
  
  - Discretização das variáveis e contínuas e codificação de todas elas propiciando aplicar cálculo das distâncias de Hamming como base do método de agrupamento utilizando Excel/Solver;

  - Agrupamento dos 50 respondentes em 5 grupos considerando semelhanças sociodemográfica e WTP, conforme abordagem de Oliveira (2015) ;
  
  - Identificação seleção de dois grupos mais promissores resultantes da etapa anterior;
  
  - Cálculo das três curvas de demanda utilizando regressão linear simples: base completa e dos dois segmentos mais promissores;
  
  -  Aplicação de otimização com Simulação de Monte Carlos com 1000 cenários para definição de preços e alocações e verba de divulgação ótimos para os objetivos de maximização de lucro, minimização de riscos ou maximização da relação retorno sobre risco (desvio padrão dos lucros esperados);
  -  
  -  Elaboração de experimento com 9 possibilidades de decisão decorrentes de dois objetivos diferentes de otimização diferentes combinados com opções de acionar todos os consumidores, consumidores do segmento 1, consumidores do segmento 2, ambos os segmentos com diferentes preços.
 
### 3. Resultados

A aplicação da metodologia destre trablho evidenciou a utilidade das aplicação de modelagem quantitativao - otimização e simulação de monte carlo - para com o processo decisório de empreendedor, mais especificamente, na desafiante tarefa de lançar um novo produto.

O software Excel e sua aplicação Solver mostraram-se suficientemente robustos para os objetivos de resolução de análise de agrupamentos e de otimização sob incerteza.

Como se vê na tabeia abaixo, a modelagem aqui proposta possibilitou armar o decisor com informações valiosas, auxiliando-o com a escolha de opções como de praticar preço de mercado, acionar um ou dois segmentos etc.


![alt text](https://github.com/VictorAmaralNeto/TCC-BI-Master-Victor-Amaral/blob/main/Imagem4.jpg)

O cenário 1 (doravantes chamado cenário-base), por exemplo, apesar de ser prática recorrente entre iniciantes em negócios, ou seja, simplesmente atribuindo o valor médio de e-books vendidos pela internet e divulgando indiscriminadamente para consumidores potenciais, mostrou-se a pior opção do experimento.

O cenário 2 é igual ao primieiro, porém praticando preço otimizado. Considerando a curva de demanda de todos os respondentes da base de dados, caso o empreendedor cobrasse R$ 70,00 ao invés de R$ 50,00, o lucro mensal final tenderia a aumentar 34% em relação ao cenário -base.

O cenário 3 tem objetivo diferente. No lugar do lucro, buscou-se otimizar a relação retorno / risco. Não houve diferença significativa em comparação com o cenário 2.

O cenário 4 representa a escolha do empreendedor em atuar apenas no segmento 2 (mulheres da classe B, região Sudeste e entre 25 e 35 anos). Neste cenário também foi aplicado o preço não otimizado de R$ 50,00. Como o segmento possui WTP maior do que a média, a lucratividade  esperada supera a do cenário 1 (mesmo conceito - base comleta) em 36%.

O cenário 5, de mesmo conceito do cenário 4, mas atuando no segmento 3 (homens da classe B, região Sudeste entre 40 e 50 anos), a lucratividade esperada foi 136% maior do que a do cenário 1. Este segmento portanto é ainda menos sensível ao preço doque o segmento 2.

O cenário 6 tratou de buscar a maxmimização do lucro combinando os dois segmentos, variando os preços e variando a alocação da verba para divulgação entre eles restrita à compra de 20.000 cliques por mês. A moldelagem indicou que neste caso o decisor deveri explorar apenas o segmento 3, com preço ótimo de R$ 104,00. A lucratividade esperada desta opção é 340% maior do que a do cenário-base.

Os cenários 7 e 8 buscaram maximizar a relação retorno/risco esperada tomando os dois segmentos isolada e respectivamente. Não houve neste caso melhora significativa em relação ao objetivo de maximização de lucro dos mesmos, mas, como esperado, a aplicação da otimização indicou cobrança de preços que propiciaram tanto o risco quanto a rentabilidade superarem siginificativamente os verificados no cenário-base.

O cenário 9 replicou o cenário 6, mas mudou o objetivo da atimização para maximização do retorno/risco. Muito embora a rentabilidade esperada tenha sido menor do que o cenário 6 (mais rentável do experimento), este cenário indicou ser mais eficiente no tratamento do risco. O indicador aqui ficou em 1,72 versus 1,48 do cenário 6. Pode-se concluir que o empreendedor menos avesso ao risco poderia optar pelo cenário 6 e um mais avesso poderia buscar a relação mais eficiente deste cenário 9. Aqui o resultado da otimização indicou que aproximadamente metade dos cliques deveria ser comprado para cada segmento e os preços ótimos praticados para o segmento 2 e 3 deveriam ser de R$ 68,00 e R$ 85,00, respectivamente.

### 4. Conclusões

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin pulvinar nisl vestibulum tortor fringilla, eget imperdiet neque condimentum. Proin vitae augue in nulla vehicula porttitor sit amet quis sapien. Nam rutrum mollis ligula, et semper justo maximus accumsan. Integer scelerisque egestas arcu, ac laoreet odio aliquet at. Sed sed bibendum dolor. Vestibulum commodo sodales erat, ut placerat nulla vulputate eu. In hac habitasse platea dictumst. Cras interdum bibendum sapien a vehicula.

Proin feugiat nulla sem. Phasellus consequat tellus a ex aliquet, quis convallis turpis blandit. Quisque auctor condimentum justo vitae pulvinar. Donec in dictum purus. Vivamus vitae aliquam ligula, at suscipit ipsum. Quisque in dolor auctor tortor facilisis maximus. Donec dapibus leo sed tincidunt aliquam.

---

Matrícula: 211.100.463

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
