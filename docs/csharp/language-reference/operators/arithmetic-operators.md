---
title: Operadores aritméticos – Referência de C#
description: Saiba mais sobre os operadores do C# que executam operações de multiplicação, divisão, resto, adição e subtração com tipos numéricos.
ms.date: 03/27/2019
author: pkulikov
f1_keywords:
- ++_CSharpKeyword
- --_CSharpKeyword
- '*_CSharpKeyword'
- /_CSharpKeyword
- '%_CSharpKeyword'
- +_CSharpKeyword
- -_CSharpKeyword
helpviewer_keywords:
- arithmetic operators [C#]
- increment operator [C#]
- ++ operator [C#]
- decrement operator [C#]
- -- operator [C#]
- multiplication operator [C#]
- '* operator [C#]'
- division operator [C#]
- / operator [C#]
- remainder operator [C#]
- '% operator [C#]'
- addition operator [C#]
- + operator [C#]
- subtraction operator [C#]
- '- operator [C#]'
ms.openlocfilehash: 192acf6fea0c6014aaf092077f8deaa844dfd2ec
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58633797"
---
# <a name="arithmetic-operators-c-reference"></a><span data-ttu-id="4ec6a-103">Operadores aritméticos (Referência de C#)</span><span class="sxs-lookup"><span data-stu-id="4ec6a-103">Arithmetic operators (C# Reference)</span></span>

<span data-ttu-id="4ec6a-104">Os seguintes operadores executam operações aritméticas com tipos numéricos:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-104">The following operators perform arithmetic operations with numeric types:</span></span>

- <span data-ttu-id="4ec6a-105">Operadores unários [`++` (incremento)](#increment-operator-), [`--` (decremento)](#decrement-operator---), [`+` (adição)](#unary-plus-and-minus-operators) e [`-` (subtração)](#unary-plus-and-minus-operators).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-105">Unary [`++` (increment)](#increment-operator-), [`--` (decrement)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators), and [`-` (minus)](#unary-plus-and-minus-operators) operators.</span></span>
- <span data-ttu-id="4ec6a-106">Operadores binários [`*` (multiplicação)](#multiplication-operator-), [`/` (divisão)](#division-operator-), [`%` (resto)](#remainder-operator-), [`+` (adição)](#addition-operator-) e [`-` (subtração)](#subtraction-operator--).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-106">Binary [`*` (multiplication)](#multiplication-operator-), [`/` (division)](#division-operator-), [`%` (remainder)](#remainder-operator-), [`+` (addition)](#addition-operator-), and [`-` (subtraction)](#subtraction-operator--) operators.</span></span>

<span data-ttu-id="4ec6a-107">Esses operadores dão suporte a todos os tipos numéricos [integrais](../keywords/integral-types-table.md) e de [ponto flutuante](../keywords/floating-point-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-107">Those operators support all [integral](../keywords/integral-types-table.md) and [floating-point](../keywords/floating-point-types-table.md) numeric types.</span></span>

## <a name="increment-operator-"></a><span data-ttu-id="4ec6a-108">Operador de incremento ++</span><span class="sxs-lookup"><span data-stu-id="4ec6a-108">Increment operator ++</span></span>

<span data-ttu-id="4ec6a-109">O operador de incremento unário `++` incrementa seu operando em 1.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-109">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="4ec6a-110">O operando precisa ser uma variável, um acesso de [propriedade](../../programming-guide/classes-and-structs/properties.md) ou um acesso de [indexador](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-110">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="4ec6a-111">Há duas formas de suporte para o operador de incremento: o operador de incremento pós-fixado, `x++`, e o operador de incremento pré-fixado, `++x`.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-111">The increment operator is supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

### <a name="postfix-increment-operator"></a><span data-ttu-id="4ec6a-112">Operador de incremento pós-fixado</span><span class="sxs-lookup"><span data-stu-id="4ec6a-112">Postfix increment operator</span></span>

<span data-ttu-id="4ec6a-113">O resultado de `x++` é o valor de `x` *antes* da operação, como mostra o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-113">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a><span data-ttu-id="4ec6a-114">Operador de incremento de prefixo</span><span class="sxs-lookup"><span data-stu-id="4ec6a-114">Prefix increment operator</span></span>

<span data-ttu-id="4ec6a-115">O resultado de `++x` é o valor de `x` *após* a operação, como mostra o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-115">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a><span data-ttu-id="4ec6a-116">Operador de decremento --</span><span class="sxs-lookup"><span data-stu-id="4ec6a-116">Decrement operator --</span></span>

<span data-ttu-id="4ec6a-117">O operador de decremento unário `--` decrementa o operando em 1.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-117">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="4ec6a-118">O operando precisa ser uma variável, um acesso de [propriedade](../../programming-guide/classes-and-structs/properties.md) ou um acesso de [indexador](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-118">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="4ec6a-119">Há duas formas de suporte para o operador de decremento: o operador de decremento pós-fixado, `x--`, e o operador de decremento pré-fixado, `--x`.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-119">The decrement operator is supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

### <a name="postfix-decrement-operator"></a><span data-ttu-id="4ec6a-120">Operador de decremento pós-fixado</span><span class="sxs-lookup"><span data-stu-id="4ec6a-120">Postfix decrement operator</span></span>

<span data-ttu-id="4ec6a-121">O resultado de `x--` é o valor de `x` *antes* da operação, como mostra o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-121">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a><span data-ttu-id="4ec6a-122">Operador de decremento de prefixo</span><span class="sxs-lookup"><span data-stu-id="4ec6a-122">Prefix decrement operator</span></span>

<span data-ttu-id="4ec6a-123">O resultado de `--x` é o valor de `x` *após* a operação, como mostra o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-123">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a><span data-ttu-id="4ec6a-124">Operadores unários de adição e subtração</span><span class="sxs-lookup"><span data-stu-id="4ec6a-124">Unary plus and minus operators</span></span>

<span data-ttu-id="4ec6a-125">O operador unário `+` retorna o valor do operando.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-125">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="4ec6a-126">O operador unário `-` calcula a negação numérica do operando.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-126">The unary `-` operator computes the numeric negation of its operand.</span></span>

[!code-csharp-interactive[unary plus and minus](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#UnaryPlusAndMinus)]

<span data-ttu-id="4ec6a-127">O operador unário `-` não dá suporte ao tipo [ulong](../keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-127">The unary `-` operator doesn't support the [ulong](../keywords/ulong.md) type.</span></span>

## <a name="multiplication-operator-"></a><span data-ttu-id="4ec6a-128">Operador de multiplicação \*</span><span class="sxs-lookup"><span data-stu-id="4ec6a-128">Multiplication operator \*</span></span>

<span data-ttu-id="4ec6a-129">O operador de multiplicação `*` calcula o produto dos operandos:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-129">The multiplication operator `*` computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication operator](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#Multiplication)]

<span data-ttu-id="4ec6a-130">O operador unário `*` é um [operador de indireção de ponteiro](multiplication-operator.md#pointer-indirection-operator).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-130">The unary `*` operator is a [pointer indirection operator](multiplication-operator.md#pointer-indirection-operator).</span></span>

## <a name="division-operator-"></a><span data-ttu-id="4ec6a-131">Operador de divisão /</span><span class="sxs-lookup"><span data-stu-id="4ec6a-131">Division operator /</span></span>

<span data-ttu-id="4ec6a-132">O operador de divisão `/` divide o primeiro operando pelo segundo.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-132">The division operator `/` divides its first operand by its second operand.</span></span>

### <a name="integer-division"></a><span data-ttu-id="4ec6a-133">Divisão de inteiros</span><span class="sxs-lookup"><span data-stu-id="4ec6a-133">Integer division</span></span>

<span data-ttu-id="4ec6a-134">Para os operandos de tipos inteiros, o resultado do operador `/` é de um tipo inteiro e igual ao quociente dos dois operandos arredondados para zero:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-134">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerDivision)]

<span data-ttu-id="4ec6a-135">Para obter o quociente dos dois operandos como um número de ponto flutuante, use o tipo `float`, `double` ou `decimal`:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-135">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a><span data-ttu-id="4ec6a-136">Divisão de ponto flutuante</span><span class="sxs-lookup"><span data-stu-id="4ec6a-136">Floating-point division</span></span>

<span data-ttu-id="4ec6a-137">Para os tipos `float`, `double` e `decimal`, o resultado do operador `/` é o quociente dos dois operandos:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-137">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointDivision)]

<span data-ttu-id="4ec6a-138">Se um dos operandos é `decimal`, outro operando não pode ser `float` nem `double`, porque nem `float` ou `double` é implicitamente conversível para `decimal`.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-138">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="4ec6a-139">Você deve converter explicitamente o operando `float` ou `double` para o tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-139">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="4ec6a-140">Para saber mais sobre as conversões implícitas entre tipos numéricos, confira a [Tabela de conversões numéricas implícitas](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-140">For more information about implicit conversions between numeric types, see [Implicit numeric conversions table](../keywords/implicit-numeric-conversions-table.md).</span></span>

## <a name="remainder-operator-"></a><span data-ttu-id="4ec6a-141">Operador de resto %</span><span class="sxs-lookup"><span data-stu-id="4ec6a-141">Remainder operator %</span></span>

<span data-ttu-id="4ec6a-142">O operador de resto `%` calcula o resto após dividir o primeiro operando pelo segundo.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-142">The remainder operator `%` computes the remainder after dividing its first operand by its second operand.</span></span>

### <a name="integer-remainder"></a><span data-ttu-id="4ec6a-143">Resto inteiro</span><span class="sxs-lookup"><span data-stu-id="4ec6a-143">Integer remainder</span></span>
  
<span data-ttu-id="4ec6a-144">Para os operandos de tipos inteiros, o resultado de `a % b` é o valor produzido por `a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-144">For the operands of integer types, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="4ec6a-145">O sinal do resto diferente de zero é o mesmo que o do primeiro operando, conforme mostra o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-145">The sign of the non-zero remainder is the same as that of the first operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerRemainder)]

<span data-ttu-id="4ec6a-146">Use o método <xref:System.Math.DivRem%2A?displayProperty=nameWithType> para calcular a divisão de inteiros e os resultados do resto.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-146">Use the <xref:System.Math.DivRem%2A?displayProperty=nameWithType> method to compute both integer division and remainder results.</span></span>

### <a name="floating-point-remainder"></a><span data-ttu-id="4ec6a-147">Resto de ponto flutuante</span><span class="sxs-lookup"><span data-stu-id="4ec6a-147">Floating-point remainder</span></span>

<span data-ttu-id="4ec6a-148">Para os operandos `float` e `double`, o resultado de `x % y` para o `x` e o `y` finitos é o valor `z` tal que</span><span class="sxs-lookup"><span data-stu-id="4ec6a-148">For the `float` and `double` operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="4ec6a-149">O sinal de `z`, se diferente de zero, é o mesmo que o sinal de `x`.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-149">The sign of `z`, if non-zero, is the same as the sign of `x`.</span></span>
- <span data-ttu-id="4ec6a-150">O valor absoluto de `z` é o valor produzido por `|x| - n * |y|`, em que `n` é o maior inteiro possível que é inferior ou igual a `|x| / |y|`, e `|x|` e `|y|` são os valores absolutos de `x` e `y`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-150">The absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="4ec6a-151">Esse método de calcular o resto é semelhante ao usado para operandos inteiros, mas é diferente do IEEE 754.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-151">This method of computing the remainder is analogous to that used for integer operands, but differs from the IEEE 754.</span></span> <span data-ttu-id="4ec6a-152">Se precisar da operação de resto em conformidade com o IEEE 754, use o método <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-152">If you need the remainder operation that complies with the IEEE 754, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="4ec6a-153">Para saber mais sobre o comportamento do operador `%` com operandos não finitos, confira a seção [Operador de restante](~/_csharplang/spec/expressions.md#remainder-operator) da [especificação da linguagem C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-153">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="4ec6a-154">Para os operandos `decimal`, o operador de resto `%` é equivalente ao [operador de resto](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) do tipo <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-154">For the `decimal` operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

<span data-ttu-id="4ec6a-155">O seguinte exemplo demonstra o comportamento do operador de resto com os operandos de ponto flutuante:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-155">The following example demonstrates the behavior of the remainder operator with floating-point operands:</span></span>

[!code-csharp-interactive[floating-point remainder](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a><span data-ttu-id="4ec6a-156">Operador de adição +</span><span class="sxs-lookup"><span data-stu-id="4ec6a-156">Addition operator +</span></span>

<span data-ttu-id="4ec6a-157">O operador de adição `+` calcula a soma dos operandos:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-157">The addition operator `+` computes the sum of its operands:</span></span>

[!code-csharp-interactive[addition operator](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#Addition)]

<span data-ttu-id="4ec6a-158">Você também pode usar o operador `+` para a combinação de delegado e concatenação de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-158">You also can use the `+` operator for string concatenation and delegate combination.</span></span> <span data-ttu-id="4ec6a-159">Para obter mais informações, confira o artigo [Operador `+`](addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-159">For more information, see the [`+` operator](addition-operator.md) article.</span></span>

## <a name="subtraction-operator--"></a><span data-ttu-id="4ec6a-160">Operador de subtração -</span><span class="sxs-lookup"><span data-stu-id="4ec6a-160">Subtraction operator -</span></span>

<span data-ttu-id="4ec6a-161">O operador de subtração `-` subtrai o segundo operando do primeiro operando:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-161">The subtraction operator `-` subtracts its second operand from its first operand:</span></span>

[!code-csharp-interactive[subtraction operator](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#Subtraction)]

<span data-ttu-id="4ec6a-162">Você também pode usar o operador `-` para a remoção de delegado.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-162">You also can use the `-` operator for delegate removal.</span></span> <span data-ttu-id="4ec6a-163">Para obter mais informações, confira o artigo [Operador `-`](subtraction-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-163">For more information, see the [`-` operator](subtraction-operator.md) article.</span></span>

## <a name="operator-precedence-and-associativity"></a><span data-ttu-id="4ec6a-164">Precedência e associatividade do operador</span><span class="sxs-lookup"><span data-stu-id="4ec6a-164">Operator precedence and associativity</span></span>

<span data-ttu-id="4ec6a-165">A seguinte lista ordena os operadores aritméticos da precedência mais alta para a mais baixa:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-165">The following list orders arithmetic operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="4ec6a-166">Operadores de incremento `x++` e decremento `x--` pós-fixados.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-166">Postfix increment `x++` and decrement `x--` operators.</span></span>
- <span data-ttu-id="4ec6a-167">Operadores de incremento `++x` e de decremento `--x` pré-fixados e operadores unários `+` e `-`.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-167">Prefix increment `++x` and decrement `--x` and unary `+` and `-` operators.</span></span>
- <span data-ttu-id="4ec6a-168">Operadores de multiplicação `*`, `/` e `%`.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-168">Multiplicative `*`, `/`, and `%` operators.</span></span>
- <span data-ttu-id="4ec6a-169">Operadores de adição `+` e `-`.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-169">Additive `+` and `-` operators.</span></span>

<span data-ttu-id="4ec6a-170">Operadores aritméticos binários são associativos à esquerda.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-170">Binary arithmetic operators are left-associative.</span></span> <span data-ttu-id="4ec6a-171">Ou seja, os operadores com o mesmo nível de precedência são avaliados da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-171">That is, operators with the same precedence level are evaluated from left to right.</span></span>

<span data-ttu-id="4ec6a-172">Use parênteses, `()`, para alterar a ordem de avaliação imposta pela precedência e pela capacidade de associação do operador.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-172">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence and associativity.</span></span>

[!code-csharp-interactive[precedence and associativity](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

<span data-ttu-id="4ec6a-173">Para obter a lista completa de operadores do C# ordenada pelo nível de precedência, confira [Operadores do C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-173">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="4ec6a-174">Atribuição composta</span><span class="sxs-lookup"><span data-stu-id="4ec6a-174">Compound assignment</span></span>

<span data-ttu-id="4ec6a-175">Para um operador binário `op`, uma expressão de atribuição composta do formato</span><span class="sxs-lookup"><span data-stu-id="4ec6a-175">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="4ec6a-176">equivale a</span><span class="sxs-lookup"><span data-stu-id="4ec6a-176">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="4ec6a-177">exceto que `x` é avaliado apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-177">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="4ec6a-178">O seguinte exemplo demonstra o uso da atribuição composta com operadores aritméticos:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-178">The following example demonstrates the usage of compound assignment with arithmetic operators:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#CompoundAssignment)]

<span data-ttu-id="4ec6a-179">Use também os operadores `+=` e `-=` para assinar e cancelar a assinatura de [eventos](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-179">You also use the `+=` and `-=` operators to subscribe to and unsubscribe from [events](../keywords/event.md).</span></span> <span data-ttu-id="4ec6a-180">Para obter mais informações, confira [Como assinar e cancelar a assinatura de eventos](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-180">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="arithmetic-overflow-and-division-by-zero"></a><span data-ttu-id="4ec6a-181">Estouro aritmético e divisão por zero</span><span class="sxs-lookup"><span data-stu-id="4ec6a-181">Arithmetic overflow and division by zero</span></span>

<span data-ttu-id="4ec6a-182">Quando o resultado de uma operação aritmética está fora do intervalo de valores finitos possíveis do tipo numérico envolvido, o comportamento de um operador aritmético depende do tipo dos operandos.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-182">When the result of an arithmetic operation is outside the range of possible finite values of the involved numeric type, the behavior of an arithmetic operator depends on the type of its operands.</span></span>

### <a name="integer-arithmetic-overflow"></a><span data-ttu-id="4ec6a-183">Estouro aritmético de inteiros</span><span class="sxs-lookup"><span data-stu-id="4ec6a-183">Integer arithmetic overflow</span></span>

<span data-ttu-id="4ec6a-184">A divisão de inteiro por zero sempre lança um <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-184">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

<span data-ttu-id="4ec6a-185">No caso de um estouro aritmético de inteiros, um contexto de verificação de estouro, que pode ser [verificado ou não verificado](../keywords/checked-and-unchecked.md), controla o comportamento resultante:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-185">In case of integer arithmetic overflow, an overflow checking context, which can be [checked or unchecked](../keywords/checked-and-unchecked.md), controls the resulting behavior:</span></span>

- <span data-ttu-id="4ec6a-186">Em um contexto verificado, se o estouro acontece em uma expressão de constante, ocorre um erro em tempo de compilação.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-186">In a checked context, if overflow happens in a constant expression, a compile-time error occurs.</span></span> <span data-ttu-id="4ec6a-187">Caso contrário, quando a operação é executada em tempo de execução, uma <xref:System.OverflowException> é gerada.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-187">Otherwise, when the operation is performed at run time, an <xref:System.OverflowException> is thrown.</span></span>
- <span data-ttu-id="4ec6a-188">Em um contexto não verificado, o resultado é truncado pelo descarte dos bits de ordem superior que não se ajustam ao tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-188">In an unchecked context, the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>

<span data-ttu-id="4ec6a-189">Juntamente com as instruções [verificadas e não verificadas](../keywords/checked-and-unchecked.md), você pode usar os operadores `checked` e `unchecked` para controlar o contexto de verificação de estouro, no qual uma expressão é avaliada:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-189">Along with the [checked and unchecked](../keywords/checked-and-unchecked.md) statements, you can use the `checked` and `unchecked` operators to control the overflow checking context, in which an expression is evaluated:</span></span>

[!code-csharp-interactive[checked and unchecked](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#CheckedUnchecked)]

<span data-ttu-id="4ec6a-190">Por padrão, as operações aritméticas ocorrem em um contexto *não verificado*.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-190">By default, arithmetic operations occur in an *unchecked* context.</span></span>

### <a name="floating-point-arithmetic-overflow"></a><span data-ttu-id="4ec6a-191">Estouro aritmético de ponto flutuante</span><span class="sxs-lookup"><span data-stu-id="4ec6a-191">Floating-point arithmetic overflow</span></span>

<span data-ttu-id="4ec6a-192">As operações aritméticas com os tipos `float` e `double` nunca geram uma exceção.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-192">Arithmetic operations with the `float` and `double` types never throw an exception.</span></span> <span data-ttu-id="4ec6a-193">O resultado de operações aritméticas com esses tipos pode ser um dos valores especiais que representam o infinito e um valor não é um número:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-193">The result of arithmetic operations with those types can be one of special values that represent infinity and not-a-number:</span></span>

[!code-csharp-interactive[double non-finite values](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointOverflow)]

<span data-ttu-id="4ec6a-194">Para os operandos do tipo `decimal`, o estouro aritmético sempre gera uma <xref:System.OverflowException> e a divisão por zero sempre gera uma <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-194">For the operands of the `decimal` type, arithmetic overflow always throws an <xref:System.OverflowException> and division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

## <a name="round-off-errors"></a><span data-ttu-id="4ec6a-195">Erros de arredondamento</span><span class="sxs-lookup"><span data-stu-id="4ec6a-195">Round-off errors</span></span>

<span data-ttu-id="4ec6a-196">Devido às limitações gerais de uma representação de ponto flutuante de números reais e da aritmética de ponto flutuante, os erros de arredondamento podem ocorrer em cálculos com tipos de ponto flutuante.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-196">Because of general limitations of the floating-point representation of real numbers and floating-point arithmetic, the round-off errors might occur in calculations with floating-point types.</span></span> <span data-ttu-id="4ec6a-197">Ou seja, o resultado produzido de uma expressão pode diferir do resultado matemático esperado.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-197">That is, the produced result of an expression might differ from the expected mathematical result.</span></span> <span data-ttu-id="4ec6a-198">O seguinte exemplo demonstra vários casos desse tipo:</span><span class="sxs-lookup"><span data-stu-id="4ec6a-198">The following example demonstrates several such cases:</span></span>

[!code-csharp-interactive[round-off errors](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#RoundOffErrors)]

<span data-ttu-id="4ec6a-199">Para obter mais informações, confira os comentários nas páginas de referência [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks) ou [System.Decimal](/dotnet/api/system.decimal#remarks).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-199">For more information, see remarks at [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks), or [System.Decimal](/dotnet/api/system.decimal#remarks) reference pages.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="4ec6a-200">Capacidade de sobrecarga do operador</span><span class="sxs-lookup"><span data-stu-id="4ec6a-200">Operator overloadability</span></span>

<span data-ttu-id="4ec6a-201">Os tipos definidos pelo usuário podem [sobrecarregar](../keywords/operator.md) os operadores aritméticos unários (`++`, `--`, `+` e `-`) e binários (`*`, `/`, `%`, `+` e `-`).</span><span class="sxs-lookup"><span data-stu-id="4ec6a-201">User-defined types can [overload](../keywords/operator.md) the unary (`++`, `--`, `+`, and `-`) and binary (`*`, `/`, `%`, `+`, and `-`) arithmetic operators.</span></span> <span data-ttu-id="4ec6a-202">Quando um operador binário está sobrecarregado, o operador de atribuição composta correspondente também é implicitamente sobrecarregado.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-202">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="4ec6a-203">Um tipo definido pelo usuário não pode sobrecarregar explicitamente um operador de atribuição composta.</span><span class="sxs-lookup"><span data-stu-id="4ec6a-203">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4ec6a-204">Especificação da linguagem C#</span><span class="sxs-lookup"><span data-stu-id="4ec6a-204">C# language specification</span></span>

<span data-ttu-id="4ec6a-205">Para obter mais informações, confira as seguintes seções da [especificação da linguagem C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="4ec6a-205">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="4ec6a-206">Operadores de incremento e decremento pós-fixados</span><span class="sxs-lookup"><span data-stu-id="4ec6a-206">Postfix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [<span data-ttu-id="4ec6a-207">Operadores de incremento e decremento pré-fixados</span><span class="sxs-lookup"><span data-stu-id="4ec6a-207">Prefix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [<span data-ttu-id="4ec6a-208">Operador unário de adição</span><span class="sxs-lookup"><span data-stu-id="4ec6a-208">Unary plus operator</span></span>](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [<span data-ttu-id="4ec6a-209">Operador unário de subtração</span><span class="sxs-lookup"><span data-stu-id="4ec6a-209">Unary minus operator</span></span>](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [<span data-ttu-id="4ec6a-210">Operador de multiplicação</span><span class="sxs-lookup"><span data-stu-id="4ec6a-210">Multiplication operator</span></span>](~/_csharplang/spec/expressions.md#multiplication-operator)
- [<span data-ttu-id="4ec6a-211">Operador de divisão</span><span class="sxs-lookup"><span data-stu-id="4ec6a-211">Division operator</span></span>](~/_csharplang/spec/expressions.md#division-operator)
- [<span data-ttu-id="4ec6a-212">Operador de resto</span><span class="sxs-lookup"><span data-stu-id="4ec6a-212">Remainder operator</span></span>](~/_csharplang/spec/expressions.md#remainder-operator)
- [<span data-ttu-id="4ec6a-213">Operador de adição</span><span class="sxs-lookup"><span data-stu-id="4ec6a-213">Addition operator</span></span>](~/_csharplang/spec/expressions.md#addition-operator)
- [<span data-ttu-id="4ec6a-214">Operador de subtração</span><span class="sxs-lookup"><span data-stu-id="4ec6a-214">Subtraction operator</span></span>](~/_csharplang/spec/expressions.md#subtraction-operator)
- [<span data-ttu-id="4ec6a-215">Atribuição composta</span><span class="sxs-lookup"><span data-stu-id="4ec6a-215">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="4ec6a-216">Os operadores verificados e não verificados</span><span class="sxs-lookup"><span data-stu-id="4ec6a-216">The checked and unchecked operators</span></span>](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)

## <a name="see-also"></a><span data-ttu-id="4ec6a-217">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4ec6a-217">See also</span></span>

- [<span data-ttu-id="4ec6a-218">Referência de C#</span><span class="sxs-lookup"><span data-stu-id="4ec6a-218">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4ec6a-219">Guia de Programação em C#</span><span class="sxs-lookup"><span data-stu-id="4ec6a-219">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4ec6a-220">Operadores do C#</span><span class="sxs-lookup"><span data-stu-id="4ec6a-220">C# Operators</span></span>](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [<span data-ttu-id="4ec6a-221">Numéricos no .NET</span><span class="sxs-lookup"><span data-stu-id="4ec6a-221">Numerics in .NET</span></span>](../../../standard/numerics.md)