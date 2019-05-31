---
title: Métricas do ML.NET
description: Entenda as métricas que são usadas para avaliar o desempenho de um modelo do ML.NET
ms.date: 04/29/2019
author: ''
ms.openlocfilehash: d76cab0b56085ebf2ee69f4d9d12c9685c3cb021
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452700"
---
# <a name="model-evaluation-metrics-in-mlnet"></a><span data-ttu-id="c9fa7-103">Métricas de avaliação de modelo do ML.NET</span><span class="sxs-lookup"><span data-stu-id="c9fa7-103">Model evaluation metrics in ML.NET</span></span>

## <a name="metrics-for-binary-classification"></a><span data-ttu-id="c9fa7-104">Métricas para classificação binária</span><span class="sxs-lookup"><span data-stu-id="c9fa7-104">Metrics for Binary Classification</span></span>

| <span data-ttu-id="c9fa7-105">Métricas</span><span class="sxs-lookup"><span data-stu-id="c9fa7-105">Metrics</span></span>   |      <span data-ttu-id="c9fa7-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="c9fa7-106">Description</span></span>      |  <span data-ttu-id="c9fa7-107">Procurar</span><span class="sxs-lookup"><span data-stu-id="c9fa7-107">Look for</span></span> |
|-----------|-----------------------|-----------|
| <span data-ttu-id="c9fa7-108">**Precisão**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-108">**Accuracy**</span></span> |  <span data-ttu-id="c9fa7-109">[Precisão](https://en.wikipedia.org/wiki/Accuracy_and_precision#In_binary_classification) é a proporção de previsões corretas com um conjunto de dados de teste.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-109">[Accuracy](https://en.wikipedia.org/wiki/Accuracy_and_precision#In_binary_classification) is the proportion of correct predictions with a test data set.</span></span> <span data-ttu-id="c9fa7-110">É a taxa do número de previsões corretas para o número total de amostras de entrada.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-110">It is the ratio of number of correct predictions to the total number of input samples.</span></span> <span data-ttu-id="c9fa7-111">Ele funcionará bem apenas se houver um número semelhante de amostras que pertencem a cada classe.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-111">It works well only if there are similar number of samples belonging to each class.</span></span>| <span data-ttu-id="c9fa7-112">**Quanto mais próximo de 1,00, melhor**.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-112">**The closer to 1.00, the better**.</span></span> <span data-ttu-id="c9fa7-113">Mas exatamente 1,00 indica um problema (geralmente: vazamento de rótulo/destino, ajuste excessivo ou teste com os dados de treinamento).</span><span class="sxs-lookup"><span data-stu-id="c9fa7-113">But exactly 1.00 indicates an issue (commonly: label/target leakage, over-fitting, or testing with training data).</span></span> <span data-ttu-id="c9fa7-114">Quando os dados de teste estão desbalanceados (em que a maioria das instâncias pertence a uma das classes), o conjunto de dados é muito pequeno ou as pontuações se aproximam de 0,00 ou 1,00, a precisão realmente não captura a eficácia de um classificador e você precisa verificar métricas adicionais.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-114">When the test data is unbalanced (where most of the instances belong to one of the classes), the dataset is very small, or scores approach 0.00 or 1.00, then accuracy doesn’t really capture the effectiveness of a classifier and you need to check additional metrics.</span></span> |
| <span data-ttu-id="c9fa7-115">**AUC**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-115">**AUC**</span></span> |    <span data-ttu-id="c9fa7-116">[aucROC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) ou *área sob a curva*: Isso está medindo a área sob a curva criada varrendo a taxa de positivos verdadeiros versus a taxa de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-116">[aucROC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) or *Area under the curve*: This is measuring the area under the curve created by sweeping the true positive rate vs. the false positive rate.</span></span>  |   <span data-ttu-id="c9fa7-117">**Quanto mais próximo de 1,00, melhor**.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-117">**The closer to 1.00, the better**.</span></span> <span data-ttu-id="c9fa7-118">Ela deve ser maior que 0.50 para que um modelo seja aceitável; um modelo com AUC de 0.50 ou menos é inútil.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-118">It should be greater than 0.50 for a model to be acceptable; a model with AUC of 0.50 or less is worthless.</span></span> |
| <span data-ttu-id="c9fa7-119">**AUCPR**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-119">**AUCPR**</span></span> | <span data-ttu-id="c9fa7-120">[aucPR](https://www.coursera.org/lecture/ml-classification/precision-recall-curve-rENu8) ou *área sob a curva de uma curva de recall de precisão*: Medida útil de sucesso da previsão quando as classes estão muito desequilibradas (conjuntos de dados altamente distorcidos).</span><span class="sxs-lookup"><span data-stu-id="c9fa7-120">[aucPR](https://www.coursera.org/lecture/ml-classification/precision-recall-curve-rENu8) or *Area under the curve of a Precision-Recall curve*: Useful measure of success of prediction when the classes are very imbalanced (highly skewed datasets).</span></span> |  <span data-ttu-id="c9fa7-121">**Quanto mais próximo de 1,00, melhor**.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-121">**The closer to 1.00, the better**.</span></span> <span data-ttu-id="c9fa7-122">Pontuações elevadas próximas de 1,00 mostram que o classificador retorna resultados precisos (precisão alta), além de retornar uma maioria de todos os resultados positivos (recall alto).</span><span class="sxs-lookup"><span data-stu-id="c9fa7-122">High scores close to 1.00 show that the classifier is returning accurate results (high precision), as well as returning a majority of all positive results (high recall).</span></span> |
| <span data-ttu-id="c9fa7-123">**Pontuação F1**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-123">**F1-score**</span></span> | <span data-ttu-id="c9fa7-124">A [pontuação F1](https://en.wikipedia.org/wiki/F1_score), também conhecida como *pontuação F balanceada ou medida F*.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-124">[F1 score](https://en.wikipedia.org/wiki/F1_score) also known as *balanced F-score or F-measure*.</span></span> <span data-ttu-id="c9fa7-125">É a média harmônica da precisão e do recall.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-125">It's the harmonic mean of the precision and recall.</span></span> <span data-ttu-id="c9fa7-126">A pontuação F1 é útil quando você deseja buscar um equilíbrio entre a precisão e o recall.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-126">F1 Score is helpful when you want to seek a balance between Precision and Recall.</span></span>| <span data-ttu-id="c9fa7-127">**Quanto mais próximo de 1,00, melhor**.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-127">**The closer to 1.00, the better**.</span></span>  <span data-ttu-id="c9fa7-128">Uma pontuação F1 atinge seu melhor valor em 1,00 e o pior em 0,00.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-128">An F1 score reaches its best value at 1.00 and worst score at 0.00.</span></span> <span data-ttu-id="c9fa7-129">Ela informa o nível de precisão do classificador.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-129">It tells you how precise your classifier is.</span></span> |

<span data-ttu-id="c9fa7-130">Para obter mais detalhes sobre as métricas de classificação binária, leia os artigos a seguir:</span><span class="sxs-lookup"><span data-stu-id="c9fa7-130">For further details on binary classification metrics read the following articles:</span></span>

- [<span data-ttu-id="c9fa7-131">Exatidão, Precisão, Recall ou F1?</span><span class="sxs-lookup"><span data-stu-id="c9fa7-131">Accuracy, Precision, Recall or F1?</span></span>](https://towardsdatascience.com/accuracy-precision-recall-or-f1-331fb37c5cb9)
- [<span data-ttu-id="c9fa7-132">Classe de métricas de classificação binária</span><span class="sxs-lookup"><span data-stu-id="c9fa7-132">Binary Classification Metrics class</span></span>](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.data.binaryclassificationmetrics?view=ml-dotnet)
- [<span data-ttu-id="c9fa7-133">A relação entre a recall de precisão e curvas ROC</span><span class="sxs-lookup"><span data-stu-id="c9fa7-133">The Relationship Between Precision-Recall and ROC Curves</span></span>](http://pages.cs.wisc.edu/~jdavis/davisgoadrichcamera2.pdf)

## <a name="metrics-for-multi-class-classification"></a><span data-ttu-id="c9fa7-134">Métricas para classificação multiclasse</span><span class="sxs-lookup"><span data-stu-id="c9fa7-134">Metrics for Multi-class Classification</span></span>

| <span data-ttu-id="c9fa7-135">Métricas</span><span class="sxs-lookup"><span data-stu-id="c9fa7-135">Metrics</span></span>   |      <span data-ttu-id="c9fa7-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="c9fa7-136">Description</span></span>      |  <span data-ttu-id="c9fa7-137">Procurar</span><span class="sxs-lookup"><span data-stu-id="c9fa7-137">Look for</span></span> |
|-----------|-----------------------|-----------|
| <span data-ttu-id="c9fa7-138">**Microprecisão**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-138">**Micro-Accuracy**</span></span> |  <span data-ttu-id="c9fa7-139">A [precisão de micromédia](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.data.multiclassclassificationmetrics.microaccuracy?view=ml-dotnet) agrega as contribuições de todas as classes para computar a métrica média.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-139">[Micro-average Accuracy](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.data.multiclassclassificationmetrics.microaccuracy?view=ml-dotnet) aggregates the contributions of all classes to compute the average metric.</span></span> <span data-ttu-id="c9fa7-140">Ela é a fração de instâncias previstas corretamente.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-140">It is the fraction of instances predicted correctly.</span></span> <span data-ttu-id="c9fa7-141">A micromédia não leva membros da classe em consideração.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-141">The micro-average does not take class membership into account.</span></span> <span data-ttu-id="c9fa7-142">Basicamente, cada par de classe de exemplo contribui igualmente para a métrica de precisão.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-142">Basically, every sample-class pair contributes equally to the accuracy metric.</span></span> | <span data-ttu-id="c9fa7-143">**Quanto mais próximo de 1,00, melhor**.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-143">**The closer to 1.00, the better**.</span></span> <span data-ttu-id="c9fa7-144">Em uma tarefa de classificação multiclasse, a microprecisão será preferível à macroprecisão se você suspeitar que há desequilíbrio de classe (ou seja,</span><span class="sxs-lookup"><span data-stu-id="c9fa7-144">In a multi-class classification task, micro-accuracy is preferable over macro-accuracy if you suspect there might be class imbalance (i.e</span></span> <span data-ttu-id="c9fa7-145">você pode ter muitos outros exemplos de uma classe do que de outras classes).</span><span class="sxs-lookup"><span data-stu-id="c9fa7-145">you may have many more examples of one class than of other classes).</span></span>|
| <span data-ttu-id="c9fa7-146">**Macroprecisão**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-146">**Macro-Accuracy**</span></span> | <span data-ttu-id="c9fa7-147">A [precisão de macromédia](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.data.multiclassclassificationmetrics.macroaccuracy?view=ml-dotnet) é a precisão média no nível de classe.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-147">[Macro-average Accuracy](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.data.multiclassclassificationmetrics.macroaccuracy?view=ml-dotnet) is the average accuracy at the class level.</span></span> <span data-ttu-id="c9fa7-148">A precisão para cada classe é calculada e a macroprecisão é a média desses precisões.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-148">The accuracy for each class is computed and the macro-accuracy is the average of these accuracies.</span></span> <span data-ttu-id="c9fa7-149">Basicamente, cada classe contribui igualmente para a métrica de precisão.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-149">Basically, every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="c9fa7-150">Classes minoritárias recebem o mesmo peso que as classes maiores.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-150">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="c9fa7-151">A métrica de macromédia fornece o mesmo peso a cada classe, não importa quantas instâncias dessa classe o conjunto de dados contém.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-151">The macro-average metric gives the same weight to each class, no matter how many instances from that class the dataset contains.</span></span> |  <span data-ttu-id="c9fa7-152">**Quanto mais próximo de 1,00, melhor**.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-152">**The closer to 1.00, the better**.</span></span>  <span data-ttu-id="c9fa7-153">Ele calcula a métrica de forma independente para cada classe e, em seguida, usa a média (tratando assim todas as classes igualmente)</span><span class="sxs-lookup"><span data-stu-id="c9fa7-153">It computes the metric independently for each class and then takes the average (hence treating all classes equally)</span></span> |
| <span data-ttu-id="c9fa7-154">**Perda logarítmica**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-154">**Log-loss**</span></span>| <span data-ttu-id="c9fa7-155">A [perda logarítmica](http://wiki.fast.ai/index.php/Log_Loss) mede o desempenho de um modelo de classificação em que a entrada de previsão é um valor de probabilidade entre 0,00 e 1,00.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-155">[Logarithmic loss](http://wiki.fast.ai/index.php/Log_Loss) measures the performance of a classification model where the prediction input is a probability value between 0.00 and 1.00.</span></span> <span data-ttu-id="c9fa7-156">A perda logarítmica aumenta à medida que a probabilidade prevista diverge do rótulo real.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-156">Log-loss increases as the predicted probability diverges from the actual label.</span></span> | <span data-ttu-id="c9fa7-157">**Quanto mais próximo de 0,00, melhor**.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-157">**The closer to 0.00, the better**.</span></span> <span data-ttu-id="c9fa7-158">Um modelo perfeito teria uma perda logarítmica de 0,00.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-158">A perfect model would have a log-loss of 0.00.</span></span> <span data-ttu-id="c9fa7-159">A meta dos nossos modelos de machine learning é minimizar esse valor.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-159">The goal of our machine learning models is to minimize this value.</span></span>|
| <span data-ttu-id="c9fa7-160">**Redução de perda logarítmica**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-160">**Log-Loss Reduction**</span></span> | <span data-ttu-id="c9fa7-161">A [redução de perda logarítmica](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.data.multiclassclassificationmetrics.loglossreduction?view=ml-dotnet) pode ser interpretada como a vantagem do classificador sobre uma previsão aleatória.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-161">[Logarithmic loss reduction](https://docs.microsoft.com/en-us/dotnet/api/microsoft.ml.data.multiclassclassificationmetrics.loglossreduction?view=ml-dotnet) can be interpreted as the advantage of the classifier over a random prediction.</span></span>| <span data-ttu-id="c9fa7-162">**Varia de -inf a 1,00, em que 1,00 é uma previsão perfeita e 0,00 indica previsões péssimas**.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-162">**Ranges from -inf and 1.00, where 1.00 is perfect predictions and 0.00 indicates mean predictions**.</span></span> <span data-ttu-id="c9fa7-163">Por exemplo, se o valor for igual a 0,20, ele poderá ser interpretado como "a probabilidade de uma previsão correta é 20% melhor do que a previsão aleatória"</span><span class="sxs-lookup"><span data-stu-id="c9fa7-163">For example, if the value equals 0.20, it can be interpreted as "the probability of a correct prediction is 20% better than random guessing"</span></span>|

<span data-ttu-id="c9fa7-164">A microprecisão geralmente se alinha melhor com as necessidades de negócios de previsões de ML.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-164">Micro-accuracy is generally better aligned with the business needs of ML predictions.</span></span> <span data-ttu-id="c9fa7-165">Se você desejar selecionar uma única métrica para escolher a qualidade de uma tarefa de classificação multiclasse, geralmente ela deverá ser microprecisão.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-165">If you want to select a single metric for choosing the quality of a multiclass classification task, it should usually be micro-accuracy.</span></span>

<span data-ttu-id="c9fa7-166">Exemplo de uma tarefa de classificação do tíquete de suporte: (mapeia tíquetes de entrada para equipes de suporte)</span><span class="sxs-lookup"><span data-stu-id="c9fa7-166">Example, for a support ticket classification task: (maps incoming tickets to support teams)</span></span>

- <span data-ttu-id="c9fa7-167">Microprecisão – com que frequência um tíquete de entrada é classificado para a equipe certa?</span><span class="sxs-lookup"><span data-stu-id="c9fa7-167">Micro-accuracy -- how often does an incoming ticket get classified to the right team?</span></span>
- <span data-ttu-id="c9fa7-168">Macroprecisão – para uma equipe de média, com que frequência um tíquete de entrada é correto para sua equipe?</span><span class="sxs-lookup"><span data-stu-id="c9fa7-168">Macro-accuracy -- for an average team, how often is an incoming ticket correct for their team?</span></span>

<span data-ttu-id="c9fa7-169">A macroprecisão sobrecarrega equipes pequenas neste exemplo; uma equipe pequena, que obtém apenas dez tíquetes por ano, conta tanto quanto uma equipe grande, com dez mil tíquetes por ano.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-169">Macro-accuracy overweights small teams in this example; a small team which gets only 10 tickets per year counts as much as a large team with 10k tickets per year.</span></span> <span data-ttu-id="c9fa7-170">Nesse caso, a microprecisão se correlaciona melhor com a necessidade de negócios de "a quantidade de tempo e dinheiro que a empresa pode salvar automatizando meu processo de roteamento de tíquetes".</span><span class="sxs-lookup"><span data-stu-id="c9fa7-170">Micro-accuracy in this case correlates better with the business need of, "how much time/money can the company save by automating my ticket routing process".</span></span>

<span data-ttu-id="c9fa7-171">Para obter mais detalhes sobre métricas de classificação multiclasse, leia os artigos a seguir:</span><span class="sxs-lookup"><span data-stu-id="c9fa7-171">For further details on multi-class classification metrics read the following articles:</span></span>

- [<span data-ttu-id="c9fa7-172">Micro e macromédia de precisão, recall e pontuação F</span><span class="sxs-lookup"><span data-stu-id="c9fa7-172">Micro- and Macro-average of Precision, Recall and F-Score</span></span>](http://rushdishams.blogspot.com/2011/08/micro-and-macro-average-of-precision.html)
- [<span data-ttu-id="c9fa7-173">Classificação multiclasse com conjunto de dados em desequilíbrio</span><span class="sxs-lookup"><span data-stu-id="c9fa7-173">Multiclass Classification with Imbalanced Dataset</span></span>](https://towardsdatascience.com/machine-learning-multiclass-classification-with-imbalanced-data-set-29f6a177c1a)

## <a name="metrics-for-regression"></a><span data-ttu-id="c9fa7-174">Métricas de regressão</span><span class="sxs-lookup"><span data-stu-id="c9fa7-174">Metrics for Regression</span></span>

| <span data-ttu-id="c9fa7-175">Métricas</span><span class="sxs-lookup"><span data-stu-id="c9fa7-175">Metrics</span></span>   |      <span data-ttu-id="c9fa7-176">Descrição</span><span class="sxs-lookup"><span data-stu-id="c9fa7-176">Description</span></span>      |  <span data-ttu-id="c9fa7-177">Procurar</span><span class="sxs-lookup"><span data-stu-id="c9fa7-177">Look for</span></span> |
|-----------|-----------------------|-----------|
| <span data-ttu-id="c9fa7-178">**R quadrado**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-178">**R-Squared**</span></span> |  <span data-ttu-id="c9fa7-179">O [R2 (R quadrado)](https://en.wikipedia.org/wiki/Coefficient_of_determination) ou *coeficiente de determinação* representa a capacidade de previsão do modelo como um valor entre -inf e 1,00.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-179">[R-squared (R2)](https://en.wikipedia.org/wiki/Coefficient_of_determination), or *Coefficient of determination* represents the predictive power of the model as a value between -inf and 1.00.</span></span> <span data-ttu-id="c9fa7-180">1,00 significa que há um ajuste perfeito e o ajuste pode ser arbitrariamente ruim, portanto, as pontuações podem ser negativas.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-180">1.00 means there is a perfect fit, and the fit can be arbitrarly poor so the scores can be negative.</span></span> <span data-ttu-id="c9fa7-181">Uma pontuação de 0,00 significa quo modelo está adivinhando o valor esperado para o rótulo.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-181">A score of 0.00 means the model is guessing the expected value for the label.</span></span> <span data-ttu-id="c9fa7-182">R2 mede o quão próximos os valores de dados de teste reais são dos valores previstos.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-182">R2 measures how close the actual test data values are to the predicted values.</span></span> | <span data-ttu-id="c9fa7-183">**Quanto mais próximo de 1,00, melhor a qualidade**.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-183">**The closer to 1.00, the better quality**.</span></span> <span data-ttu-id="c9fa7-184">No entanto, às vezes, valores de R quadrado baixos (por exemplo, 0,50) podem ser totalmente normais suficientemente bons para seu cenário, enquanto valores de R quadrado altos nem sempre são bons. Convém sempre suspeitar.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-184">However, sometimes low R-squared values (such as 0.50) can be entirely normal or good enough for your scenario and high R-squared values are not always good and be suspicious.</span></span> |
| <span data-ttu-id="c9fa7-185">**Perda absoluta**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-185">**Absolute-loss**</span></span> |  <span data-ttu-id="c9fa7-186">A [perda absoluta](https://en.wikipedia.org/wiki/Mean_absolute_error) ou *MAE (erro de média absoluta)* mede o quão próximas as previsões são dos resultados reais.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-186">[Absolute-loss](https://en.wikipedia.org/wiki/Mean_absolute_error) or *Mean absolute error (MAE)* measures how close the predictions are to the actual outcomes.</span></span> <span data-ttu-id="c9fa7-187">É a média de todos os erros do modelo, em que o erro do modelo é a distância absoluta entre o valor de rótulo previsto e o valor de rótulo correto.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-187">It is the average of all the model errors, where model error is the absolute distance between the predicted label value and the correct label value.</span></span> <span data-ttu-id="c9fa7-188">Esse erro de previsão é calculado para cada registro do conjunto de dados de teste.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-188">This prediction error is calculated for each record of the test data set.</span></span> <span data-ttu-id="c9fa7-189">Por fim, o valor médio é calculado para todos os erros absolutos gravados.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-189">Finally, the mean value is calculated for all recorded absolute errors.</span></span>| <span data-ttu-id="c9fa7-190">**Quanto mais próximo de 0,00, melhor a qualidade.**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-190">**The closer to 0.00, the better quality.**</span></span> <span data-ttu-id="c9fa7-191">Observe que o erro de média absoluta usa a mesma escala que os dados que estão sendo medidos (não são normalizados para o intervalo específico).</span><span class="sxs-lookup"><span data-stu-id="c9fa7-191">Note that the mean absolute error uses the same scale as the data being measured (is not normalized to specific range).</span></span> <span data-ttu-id="c9fa7-192">Perda absoluta, perda quadrática e perda de RMS somente podem ser usadas para fazer comparações entre modelos para o mesmo conjunto de dados ou com um conjunto de dados com uma distribuição de valor de rótulo similar.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-192">Absolute-loss, Squared-loss, and RMS-loss can only be used to make comparisons between models for the same dataset or dataset with a smilar label value distribution.</span></span> |
| <span data-ttu-id="c9fa7-193">**Perda quadrática**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-193">**Squared-loss**</span></span> |  <span data-ttu-id="c9fa7-194">[Perda quadrática](https://en.wikipedia.org/wiki/Mean_squared_error) ou *MSE (erro médio quadrático)*, também chamado de *MSD (desvio médio quadrático)*, informa como fechar uma linha de regressão é para um conjunto de valores de dados de teste.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-194">[Squared-loss](https://en.wikipedia.org/wiki/Mean_squared_error) or *Mean Squared Error (MSE)*, also called or *Mean Squared Deviation (MSD)* tells you how close a regression line is to a set of test data values.</span></span> <span data-ttu-id="c9fa7-195">Ele faz isso utilizando as distâncias entre os pontos e a linha de regressão (essas distâncias são "erros") e elevando-as ao quadrado.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-195">It does this by taking the distances from the points to the regression line (these distances are the “errors”) and squaring them.</span></span> <span data-ttu-id="c9fa7-196">Elevar ao quadrado dá mais peso para diferenças maiores.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-196">The squaring gives more weight to larger differences.</span></span> | <span data-ttu-id="c9fa7-197">É sempre positivo, e **valores mais próximos de 0,00 são melhores**.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-197">It is always non-negative, and **values closer to 0.00 are better**.</span></span> <span data-ttu-id="c9fa7-198">Dependendo de seus dados, pode ser impossível obter um valor muito pequeno para o erro médio quadrático.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-198">Depending on your data, it may be impossible to get a very small value for the mean squared error.</span></span>|
| <span data-ttu-id="c9fa7-199">**Perda de RMS**</span><span class="sxs-lookup"><span data-stu-id="c9fa7-199">**RMS-loss**</span></span> |  <span data-ttu-id="c9fa7-200">A [perda de RMS](https://en.wikipedia.org/wiki/Root-mean-square_deviation) ou *RMSE (raiz do erro médio quadrático)*, também chamada de *RMSD (raiz do desvio médio quadrático*), mede a diferença entre valores previstos por um modelo e os valores realmente observados no ambiente que está sendo modelado.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-200">[RMS-loss](https://en.wikipedia.org/wiki/Root-mean-square_deviation) or *Root Mean Squared Error (RMSE)* (also called *Root Mean Square Deviation, RMSD*), measures the difference between values predicted by a model and the values actually observed from the environment that is being modeled.</span></span> <span data-ttu-id="c9fa7-201">A perda de RMS é a raiz quadrada da perda quadrática e tem as mesmas unidades que o rótulo, de modo semelhante à perda absoluta, mas dando mais peso para diferenças maiores.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-201">RMS-loss is the square root of Squared-loss and has the same units as the label, similar to the abolute-loss though giving more weight to larger diferences.</span></span> <span data-ttu-id="c9fa7-202">A raiz do erro médio quadrático normalmente é usada em climatologia, previsão e análise de regressão para verificar resultados experimentais.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-202">Root mean square error is commonly used in climatology, forecasting, and regression analysis to verify experimental results.</span></span> | <span data-ttu-id="c9fa7-203">É sempre positivo, e **valores mais próximos de 0,00 são melhores**.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-203">It is always non-negative, and **values closer to 0.00 are better**.</span></span> <span data-ttu-id="c9fa7-204">RMSD é uma medida de precisão, para comparar os erros de previsão de modelos diferentes para um conjunto de dados específico e não entre conjuntos de dados, já que ela é dependente de escala.</span><span class="sxs-lookup"><span data-stu-id="c9fa7-204">RMSD is a measure of accuracy, to compare forecasting errors of different models for a particular dataset and not between datasets, as it is scale-dependent.</span></span>|

<span data-ttu-id="c9fa7-205">Para obter mais detalhes sobre as métricas de regressão, leia os artigos a seguir:</span><span class="sxs-lookup"><span data-stu-id="c9fa7-205">For further details on regression metrics, read the following articles:</span></span>

- [<span data-ttu-id="c9fa7-206">Análise de regressão: como interpretar R quadrado e avaliar a adequação do ajuste?</span><span class="sxs-lookup"><span data-stu-id="c9fa7-206">Regression Analysis: How Do I Interpret R-squared and Assess the Goodness-of-Fit?</span></span>](https://blog.minitab.com/blog/adventures-in-statistics-2/regression-analysis-how-do-i-interpret-r-squared-and-assess-the-goodness-of-fit)
- [<span data-ttu-id="c9fa7-207">Como interpretar R quadrado na análise de regressão</span><span class="sxs-lookup"><span data-stu-id="c9fa7-207">How To Interpret R-squared in Regression Analysis</span></span>](https://statisticsbyjim.com/regression/interpret-r-squared-regression)
- [<span data-ttu-id="c9fa7-208">Definição de R quadrado</span><span class="sxs-lookup"><span data-stu-id="c9fa7-208">R-Squared Definition</span></span>](https://www.investopedia.com/terms/r/r-squared.asp)
- [<span data-ttu-id="c9fa7-209">Definição de erro médio quadrático</span><span class="sxs-lookup"><span data-stu-id="c9fa7-209">Mean Squared Error Definition</span></span>](https://www.statisticshowto.datasciencecentral.com/mean-squared-error/)
- [<span data-ttu-id="c9fa7-210">O que são o erro médio quadrático e a raiz do erro médio quadrático?</span><span class="sxs-lookup"><span data-stu-id="c9fa7-210">What are Mean Squared Error and Root Mean Squared Error?</span></span>](https://www.vernier.com/til/1014/)