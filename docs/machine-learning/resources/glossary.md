---
title: Glossário de aprendizado de máquina – ML.NET
description: Um glossário de termos essenciais sobre o aprendizado de máquina, que são úteis ao criar seus modelos personalizados no ML.NET.
ms.custom: seodec18
ms.date: 03/05/2019
ms.openlocfilehash: cc236aaa99fd8a7b05af666a5b96f657d8bd3ad4
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410232"
---
# <a name="machine-learning-glossary-of-important-terms"></a>Glossário de aprendizado de máquina com termos importantes

A lista a seguir é uma compilação de termos essenciais sobre o aprendizado de máquina, que são úteis ao criar seus modelos personalizados no ML.NET.

> [!NOTE]
> Esta documentação refere-se ao ML.NET, que está atualmente em versão prévia. O material pode estar sujeito a alterações. Para obter mais informações, confira a [Introdução ao ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

## <a name="accuracy"></a>Precisão

Na [classificação](#classification), a precisão consiste no número de itens classificados corretamente dividido pelo número total de itens no conjunto de testes. Varia de 0 (menos preciso) a 1 (mais preciso). A precisão é uma das métricas de avaliação do desempenho do modelo. Considere isso em conjunção com [precisão](#precision), [recall](#recall)e [F-score](#f-score).

## <a name="area-under-the-curve-auc"></a>Área sob a curva (AUC)

Na [classificação binária](#binary-classification), uma métrica de avaliação que é o valor da área sob a curva que plota a taxa de positivos reais (no eixo y) em relação à taxa de falsos positivos (no eixo x). Varia de 0,5 (pior) a 1 (melhor). Também conhecida como a área sob a curva ROC, isto é, a curva característica de operação do receptor. Para obter mais informações, consulte o artigo [Característica de operação do receptor](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) na Wikipédia.

## <a name="binary-classification"></a>Classificação binária

Um caso de [classificação](#classification), em que o [rótulo](#label) é apenas uma das duas classes. Para saber mais, confira a seção [Classificação binária](tasks.md#binary-classification) do tópico [Tarefas de aprendizado de máquina](tasks.md).

## <a name="classification"></a>Classificação

Quando os dados são usados ​​para prever uma categoria, a tarefa de [aprendizado de máquina supervisionado](#supervised-machine-learning) é chamada de classificação. [Classificação binária](#binary-classification) refere-se à previsão de apenas duas categorias (por exemplo, classificar uma imagem como uma figura de um "gato" ou um "cachorro"). [Classificação multiclasse](#multiclass-classification) refere-se à previsão de várias categorias (por exemplo, ao classificar uma imagem como uma imagem de uma raça específica de cão).

## <a name="coefficient-of-determination"></a>Coeficiente de determinação

Na [regressão](#regression), uma métrica de avaliação que indica como os dados se ajustam a um modelo. Varia de 0 a 1. Um valor de 0 significa que os dados são aleatórios ou não podem ser ajustados ao modelo. Um valor de 1 significa que o modelo corresponde exatamente aos dados. Geralmente denominado como r<sup>2</sup>, R<sup>2</sup>, ou r-quadrado.

## <a name="feature"></a>Recurso

Uma propriedade mensurável do fenômeno que está sendo medido, normalmente um valor numérico (duplo). Vários recursos são referidos como **Vetor de recursos** e normalmente armazenados como `double[]`. As características definem as características importantes do fenômeno que está sendo medido. Para obter mais informações, consulte o artigo [Recurso](https://en.wikipedia.org/wiki/Feature_(machine_learning)) na Wikipédia.

## <a name="feature-engineering"></a>Engenharia de recursos

A engenharia de recursos é o processo que envolve a definição de um conjunto de [recursos](#feature) e o desenvolvimento de software que produz vetores de recursos a partir de dados de fenômenos disponíveis, ou seja, a extração de recursos. Para obter mais informações, consulte o artigo [Engenharia de recursos](https://en.wikipedia.org/wiki/Feature_engineering) na Wikipédia.

## <a name="f-score"></a>F-score

Na [classificação](#classification), uma métrica de avaliação que equilibra [precisão](#precision) e [recall](#recall).

## <a name="hyperparameter"></a>Hiperparâmetro

Um parâmetro de um algoritmo de aprendizado de máquina. Os exemplos incluem o número de árvores a serem aprendidas em uma floresta de decisão ou o tamanho da etapa em um algoritmo descendente de gradiente. Os valores de *Hiperparâmetros* são definidos antes de treinar o modelo e controlar o processo de localização dos parâmetros da função de previsão, por exemplo, os pontos de comparação em uma árvore de decisão ou os pesos em um modelo de regressão linear. Para obter mais informações, consulte o artigo [Hiperparâmetro](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning)) na Wikipédia.

## <a name="label"></a>Rotular

O elemento a ser previsto com o modelo de aprendizado de máquina. Por exemplo, a raça do cão ou um preço futuro da ação.

## <a name="log-loss"></a>Perda de log

Na [classificação](#classification), uma métrica de avaliação que caracteriza a precisão de um classificador. Quanto menor a perda de log, mais preciso é um classificador.

## <a name="mean-absolute-error-mae"></a>Erro de média absoluta (MAE)

Na [regressão](#regression), uma métrica de avaliação que é a média de todos os erros de modelo, em que erro de modelo consiste na distância entre o valor do [rótulo](#label) previsto e o valor do rótulo correto.

## <a name="model"></a>Modelo

Tradicionalmente, os parâmetros para a função de previsão. Por exemplo, os pesos em um modelo de regressão linear ou os pontos de divisão em uma árvore de decisão. No ML.NET, um modelo contém todas as informações necessárias para prever o [rótulo](#label) de um objeto de domínio (por exemplo, imagem ou texto). Isso significa que os modelos ML.NET incluem as etapas de personalização necessárias, bem como os parâmetros para a função de previsão.

## <a name="multiclass-classification"></a>Classificação multiclasse

Um caso de [classificação](#classification) em que o [rótulo](#label) é uma entre três ou mais classes. Para saber mais, confira a seção [Classificação multiclasse](tasks.md#multiclass-classification) do tópico [Tarefas de aprendizado de máquina](tasks.md).

## <a name="n-gram"></a>N-grama

Um esquema de extração de recursos para dados de texto: qualquer sequência de N palavras se transforma em um valor de [recurso](#feature).

## <a name="numerical-feature-vector"></a>Vetor de recurso numérico

Um vetor de [recurso](#feature) consistindo apenas em valores numéricos. Similar ao `double[]`.

## <a name="pipeline"></a>Pipeline

Todas as operações necessárias para ajustar um modelo a um conjunto de dados. Um pipeline consiste em etapas de importação, transformação, personalização e aprendizado de dados. Uma vez que um pipeline é treinado, ele se torna um modelo.

## <a name="precision"></a>Precisão

Na [classificação](#classification), a precisão de uma classe é o número de itens preditos corretamente como pertencentes a essa classe dividido pelo número total de itens previstos como pertencentes à classe.

## <a name="recall"></a>Recall

Na [classificação](#classification), o recall de uma classe é o número de itens preditos corretamente como pertencentes a essa classe dividido pelo número total de itens que realmente pertencem à classe.

## <a name="regression"></a>Regressão

Uma tarefa de [aprendizado de máquina supervisionado](#supervised-machine-learning) em que a saída é um valor real, por exemplo, duplo. Exemplos incluem a previsão de preços de ações. Para saber mais, confira a seção [Regressão](tasks.md#regression) do tópico [Tarefas de aprendizado de máquina](tasks.md).

## <a name="relative-absolute-error"></a>Erro absoluto relativo

Na [regressão](#regression), uma métrica de avaliação que é a soma de todos os erros absolutos dividida pela soma das distâncias entre os valores de [rótulo](#label) corretos e a média de todos os valores de rótulo corretos.

## <a name="relative-squared-error"></a>Erro quadrático relativo

Na [regressão](#regression), uma métrica de avaliação que é a soma de todos os erros absolutos quadráticos dividida pela soma das distâncias quadráticas entre os valores de [rótulo](#label) corretos e a média de todos os valores de rótulo corretos.

## <a name="root-of-mean-squared-error-rmse"></a>Raiz do erro quadrático médio (RMSE)

Na [regressão](#regression), uma métrica de avaliação que é a raiz quadrada da média dos quadrados dos erros.

## <a name="supervised-machine-learning"></a>Aprendizado de máquina supervisionado

Uma subclasse de aprendizado de máquina na qual um modelo desejado prevê o rótulo para dados ainda não vistos. Exemplos incluem a classificação, regressão e previsão estruturada. Para obter mais informações, consulte o artigo [Aprendizado supervisionado](https://en.wikipedia.org/wiki/Supervised_learning) na Wikipédia.

## <a name="training"></a>Treinamento

O processo de identificar um [modelo](#model) para um determinado conjunto de dados de treinamento. Para um modelo linear, isso significa encontrar os pesos. Para uma árvore, isso envolve a identificação dos pontos de divisão.

## <a name="transform"></a>Transformar

Um componente do [pipeline](#pipeline) que transforma dados. Por exemplo, de texto para vetor de números.

## <a name="unsupervised-machine-learning"></a>Aprendizado de máquina não supervisionado

Uma subclasse de aprendizado de máquina na qual um modelo desejado encontra estrutura oculta (ou latente) nos dados. Exemplos incluem clustering, modelagem de tópico e redução de dimensionalidade. Para obter mais informações, consulte o artigo [Aprendizado não supervisionado](https://en.wikipedia.org/wiki/Unsupervised_learning) na Wikipédia.
