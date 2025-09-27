# 🩺 Pima Indians Diabetes — Machine Learning Notebook

(1)Descrição do Projeto
    Este projeto desenvolve um modelo de Machine Learning para prever a presença de diabetes em pacientes, utilizando o dataset "Pima Indians Diabetes Database". O principal classificador explorado é o Support Vector Machine (SVM).

    O foco central do estudo é a otimização de hiperparâmetros através do GridSearchCV, com uma análise comparativa rigorosa entre duas estratégias de validação cruzada: KFold(10) e StratifiedKFold(3). O objetivo é demonstrar a importância da estratificação em datasets com classes desbalanceadas para obter uma estimativa de performance mais confiável e, consequentemente, um modelo final mais robusto.

(2)Metodologia
    O projeto foi estruturado seguindo as seguintes etapas:

        ✔️ Carga e Divisão dos Dados: O dataset foi carregado e dividido em conjuntos de treino (80%) e teste (20%). A divisão foi feita de forma estratificada para garantir que a proporção de pacientes diabéticos e não diabéticos fosse mantida em ambos os conjuntos.
        
        ✔️ Pipeline de Pré-processamento: Foi construído um Pipeline para automatizar o tratamento dos dados, incluindo:
        StandardScaler: Para padronizar as features, garantindo que todas tenham a mesma escala.
        
        ✔️ Otimização e Comparação com GridSearchCV: O GridSearchCV foi utilizado para testar exaustivamente diferentes combinações de hiperparâmetros do SVM (kernel, C, gamma). Este processo foi executado duas vezes para comparar as seguintes estratégias de validação:
        KFold com 10 splits: Uma validação cruzada padrão.
        StratifiedKFold com 3 splits: Uma validação que preserva a proporção das classes em cada fold.
        
        ✔️ Treinamento e Avaliação do Modelo Final: Após a otimização, o melhor conjunto de hiperparâmetros (kernel='rbf', C=10, gamma=0.01) foi usado para treinar um modelo final com todos os dados de treino. O desempenho deste modelo foi então avaliado no conjunto de teste, utilizando métricas como acurácia, matriz de confusão e o classification_report (com precisão, recall e F1-score).
        
        ✔️ Visualização da Fronteira de Decisão: Para uma análise mais intuitiva, foi gerado um gráfico que plota a fronteira de decisão do modelo SVM, mostrando como ele separa os pacientes com base nas duas features mais relevantes (Glucose e BMI).

(3)Pré-requisitos e Instalação
    A grande vantagem de usar o Google Colab é que ele já vem com o ambiente pronto, simplificando muito a configuração.

    Pré-requisitos:

        Google Colab;
        python.

    Bibliotecas:
            pandas;
            scikit-learn;
            Numpy;
            Matplotlib.

(4)Resultados e Análise
    A etapa de GridSearchCV revelou que a melhor combinação de hiperparâmetros foi {'clf__kernel': 'rbf', 'clf__C': 10, 'clf__gamma': 0.01} para ambas as estratégias de validação cruzada.

    O modelo final, treinado com estes parâmetros, alcançou uma acurácia de aproximadamente 75.32% no conjunto de teste. A análise detalhada do classification_report mostra que o modelo possui um bom equilíbrio entre precisão e recall, sendo o recall para a classe "diabético" uma métrica de especial importância clínica, pois indica a capacidade do modelo de identificar corretamente os pacientes que de fato possuem a doença.

    Matriz de Confusão
    A matriz de confusão ilustra a distribuição de acertos e erros do modelo no conjunto de teste.

![matriz de confusao.png](matriz%20de%20confusao.png)

    Decisão do SVM
    o kernel RBF cria uma fronteira de decisão não-linear para separar as classes, utilizando as features Glucose e BMI. Os pontos circulados representam os vetores de suporte, que são os dados mais influentes para a definição do modelo.


(6)Ferramentas Utilizadas
        Linguagem: 
        Python 3

    Bibliotecas:
        Pandas;
        Numpy;
        Scikit-learn;
        Matplotlib.
