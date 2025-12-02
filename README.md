# PP3 - Classificação de nível de obesidade com base nos hábitos alimentares e na condição física
## Equipe:
- Alexandro Pantoja Dos Santos
- Aline Daffiny Ferreira Gomes
- Eduardo Peres de Lima
- Oziel Bezerra De Lima
- Pedro Yutaro Mont Morency Nakamura

## Estrutura do Repositório
```
Dataset                                            #pasta com os datasets usados
  \ObesityDataSet_raw_and_data_sinthetic.csv            #dataset original
  \dataset_tratado.csv                                  #dataset pós-tratamento
Fine Tuning                                        #pasta com os notebooks relacionados a fine tuning
  \tuning_optuna.ipynb                                  #notebook de tuning com optuna
Resultados                                         #pasta com os resultados do grid search
  \Alexandro                                            #pasta com os resultados da grid com SGD
  \Eduardo                                              #pasta com os resultados da grid com Adam
analise_tratamento_dados.ipynb                     #notebook com a análise exploratório do dataset e tratamento dos dados
grid_search.ipynb                                  #notebook com a busca em grade
```

## O Problema
Neste trabalho é abordado o problema de estimar o grau de obesidade de indivíduos a partir de seus hábitos alimentares e de fatores físicos. O dataset utilizado é composto por 2.111 instâncias e 17 atributos, contendo variáveis relacionadas a características pessoais, rotina alimentar, hábitos diários e atividade física. A partir desses dados foi desenvolvido uma rede neural MLP com o objetivo de produzir predições confiáveis sobre o nível de obesidade de novos indivíduos.  
A solução proposta é relevante por oferecer uma abordagem computacional eficiente para apoiar o diagnóstico precoce e o monitoramento de níveis de obesidade, um problema de saúde pública que cresce globalmente. O modelo proposto pode auxiliar profissionais de saúde e sistemas automatizados a identificar indivíduos em risco com maior precisão e rapidez. Ademais, ferramentas desse tipo podem ser integradas a plataformas de bem-estar e aplicativos de acompanhamento, permitindo intervenções personalizadas e contribuindo para estratégias preventivas mais eficazes.

## Determinação da Tarefa
A variável alvo são as classes de pesos, variando de “Insufficient Weight” até “Obesity Type III”, portanto a tarefa se enquadra como **Classficação Multiclasse**.

## Abordagem de Validação Cruzada
A abordagem de **K-Fold** foi escolhida devido a natureza do dataset, com poucos dados disponíveis, garantindo que todas as *folds* serão eventualmente usadas, tanto para treino quanto para teste.

## Determinação das Métricas
A métrica escolhida é a F1 Macro, por dar o mesmo peso para todas as classes, independente do balanceamento, evita que classes mais frequentes dominem o resultado da métrica.
