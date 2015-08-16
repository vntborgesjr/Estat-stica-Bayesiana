# Introdução ao WinBUGS para Ecólogos

## Capítulo 1 – Introdução

### Inferência Bayesiana

A inferência Bayesiana é baseada na distribuição posterior, a qual expressa tudo que se sabe sobre os parâmetros de um modelo estatístico, dado o conjunto de dados e o conhecimento prévio (a priori) sobre os parâmetros.

### Vantagens da Abordagem Bayesiana Sobre a Estatística Clássica

A interpretação da probabilidade sob o paradigma Bayesiano é muito mais intuitivo do que na abordagem frequentista clássica; calcula-se diretamente a probabilidade de que um parâmetro apresenta um determinado valor, ao em vez de calcular a probabilidade de se obter um conjunto de dados, dado um modelo nulo. Afirmativas como “estamos 99% certos de que...” somente são possíveis sob a perspectiva Bayesiana. Isso porque na abordagem Bayesiana, as afirmativas são feitas sobre a probabilidade dos parâmetros, enquanto na abordagem frequentista clássica as afirmativas são feitas sobre a probabilidade do conjunto de dados.
Além disso, as conclusões baseadas no conhecimento prévio (a priori) e no que se sabe agora (o conjunto de dados), a estatística Bayesiana representa a formalização matemática do processo de aprendizagem.

### Semelhanças Entre a Estatística Bayesiana e a Clássica

Tanto a estatística clássica quanto a bayesiana veem os dados como observações realizadas de sistemas estocásticos que contem um, ou diversos processos aleatórios. 

### Diferenças e Vantagens Entre a Estatística Bayesiana e a Clássica

Na estatística clássica, as quantidades utilizadas para descrever esses processos aleatórios (parâmetros) são constantes fixas e desconhecidas, enquanto na estatística bayesianos parâmetros são vistos como observações não realizadas desses processos aleatórios. Na estatística clássica, a incerteza é avaliada e descrita em termos da frequência de réplicas hipotéticas, embora essas inferências sejam tipicamente descritas a partir do conhecimento de um único conjunto de dados. Por isso, a estatística clássica também é conhecida como estatística frequentista. Na estatística bayesiana, a incerteza é avaliada utilizando a distribuição posterior do parâmetro, a qual é condicional a distribuição de probabilidades das quantidades desconhecidas (parâmetros), dado o conjunto de dados, o modelo e o que nós sabemos sobre essas quantidades (parâmetros) antes de conduzir a análise (a priori).
Em outras palavras, as estatísticas clássica e bayesiana diferem na definição de probabilidade. Na estatística clássica, a probabilidade é a frequência relativa de uma característica do conjunto de dados. Em contraste, na estatística bayesiana a probabilidade é utilizada para expressar a incerteza sobre a provável magnitude de um parâmetro; não são necessárias réplicas hipotéticas do conjunto de dados. 
Adicionalmente, a inferência clássica baseada no máxima verossimilhança (maximum likelihood) não apresenta viés com amostras grandes, porém pode ser bastante enviesada para tamanhos amostrais pequenos. A inferência Bayesiana, por sua vez, é exata para qualquer tamanho amostral. 

## Capítulo 2 – Introdução a Análise Bayesiana de um Modelo Estatístico

### Teoria da Probabilidade e Estatística

Tanto a teoria da probabilidade quanto a estatística lidam com as características de um sistema estocástico (parâmetros do modelo) e seus resultados (conjunto de dados observados), mas esses dois campos representam diferentes perspectivas sobre os sistemas estocásticos. A teoria da probabilidade especifica os parâmetro, um modelo e examina os variáveis resultados obtidos, enquanto a estatística utiliza um conjunto de dados, assume um modelo e tenta inferir as propriedades de um sistema a partir deste modelo. Portanto, a estatística lida com a realização de inferências (conclusões probabilísticas sobre os parâmetros que compõem o sistema) baseada no modelo e nas observações obtidas a partir de um sistema estocástico. 

### Duas Abordagens da Estatística: Clássica e Bayesiana

Ambas as abordagens, clássica e bayesiana, consideram os dados como observações realizadas de sistemas estocásticos que contém um ou mais processos aleatórios. Entretanto, na estatística clássica as quantidades utilizadas para descrever os processos aleatórios (parâmetros) são constantes fixas e desconhecidas, enquanto na estatística bayesiana os parâmetros são vistos como realizações não observadas desses processos aleatórios. Na estatística clássica, a incerteza é avaliada e descrita em termos da frequência de réplicas hipotéticas, embora essas inferências sejam tipicamente descritas somente a partir do conhecimento de um único conjunto de dados. Por isso, a estatística clássica também é chamada de frequnetista. Na estatística bayesiana, a incerteza é avaliada utilizando a distribuição posterior do parâmetro, que é a distribuição de probabilidade condicional de todas as quantidades desconhecidas (ex. parâmetros), dado o conjunto de dados, o modelo e o que se sabe sobre essas quantidades antes de se conduzir as análises.
Em outras palavras, as estatísticas clássica e bayesiana diferem em suas definições de probabilidade. Na estatística clássica, a probabilidade é a frequência relativa de uma característica dos dados observados. Na estatística bayesiana, a probabilidade é utilizada para expressar a incerteza sobre a possível magnitude de um parâmetro; não são necessárias replicas hipotéticas do conjunto de dados.
Sob a inferência bayesiana, nós distinguimos quantidades observadas (dados) de quantidades não observadas (parâmetros). Todas as quantidades não observadas são consideradas variáveis aleatórias, ou seja quantidades que só podem ser determinadas probabilisticamente. Sob o paradigma bayesiano é possível realizar afirmações probabilísticas sobre os parâmetros estimados (ex. a probabilidade de que a população está declinando é de 24%). Sob a abordagem clássica da estatística não é impossível realizar tal afirmação por principio porque os parâmetros são fixos e somente os dados são aleatórios.
Enquanto a estatística clássica trabalha estimando um único ponto para o valor de um parâmetro (que é uma constante desconhecida), a estatística bayesiana realiza a inferência sobre a distribuição do parâmetro, porque estes são variáveis aleatórias descritas por uma distribuição estatística.

### A Importância de Algoritmos Modernos e de Computadores para a Estatística Bayesiana
### Markov Chain Monte Carlo e Amostragem de Gibbs

MCMC é um conjunto de técnicas utilizado para realizar amostragens da da distribuição posterior p(Θ|x) dado o modelo, a verossimilhança p(x|Θ) e os dados x, utilizando uma sequencia dependente de variáveis aleatórias. 
Sumário simplista da análise estatística bayesiana até o momento:

 1. Utilizamos a definição de probabilidade baseada no grau de credibilidade ao em vez de utilizar a definição baseada na frequência de eventos entre réplicas hipotéticas.
 2. Utilizamos a distribuição de probabilidade para sumarizar a credibilidade e o conhecimento (ou falta dele) sobre cada parâmetro do modelo e aplicamos a regra de Bayes para atualizar esse conhecimento com os dados observados e obter a distribuição posterior de cada parâmetro desconhecido no modelo. A distribuição posterior quantifica todo nosso conhecimento sobre os parâmetros dado os dados, o modelo e o conhecimento prévio. Toda inferência estatística é baseada na distribuição posterior.
 3. Entretanto, a distribuição posterior é impossível de se computar analiticamente, exceto nos casos mais simples; utilizamos então uma simulação (MCMC) para amostrar uma série de amostras dependentes a partir da distribuição posterior e baseamos nossa inferência nessa amostra.

### O que vem depois do MCMC?
### Monitorando a convergência
### Sumarizando a distribuição posterior para inferência
### Computando funções de parâmetros
### Formulando previsões
### Alguns desafios compartilhados entre a análise bayesiana e clássica de um modelo estatístico