---
title: Operadores sobrecarregáveis – Guia de Programação em C#
ms.custom: seodec18
ms.date: 08/27/2018
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
ms.openlocfilehash: d0a5555bbe68aa82218c1dbe3d24705b26aff9c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296570"
---
# <a name="overloadable-operators-c-programming-guide"></a>Operadores sobrecarregáveis (Guia de Programação em C#)

O C# permite que tipos definidos pelo usuário sobrecarreguem operadores definindo funções de membro estático usando a palavra-chave [operator](../../language-reference/keywords/operator.md). No entanto, nem todos os operadores podem ser sobrecarregados e outros têm restrições, conforme listado nesta tabela:

| Operadores | Capacidade de sobrecarga |
| --------- | --------------- |
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [!](../../language-reference/operators/boolean-logical-operators.md#logical-negation-operator-), [~](../../language-reference/operators/bitwise-complement-operator.md), [++](../../language-reference/operators/arithmetic-operators.md#increment-operator-), [--](../../language-reference/operators/arithmetic-operators.md#decrement-operator---), [true](../../language-reference/keywords/true-false-operators.md), [false](../../language-reference/keywords/true-false-operators.md)|Esses operadores unários podem ser sobrecarregados.|
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [\*](../../language-reference/operators/arithmetic-operators.md#multiplication-operator-), [/](../../language-reference/operators/arithmetic-operators.md#division-operator-), [%](../../language-reference/operators/arithmetic-operators.md#remainder-operator-), [&](../../language-reference/operators/and-operator.md), [&#124;](../../language-reference/operators/or-operator.md), [^](../../language-reference/operators/xor-operator.md), [\<\<](../../language-reference/operators/left-shift-operator.md), [>>](../../language-reference/operators/right-shift-operator.md)|Esses operadores binários podem ser sobrecarregados.|
|[==](../../language-reference/operators/equality-operators.md#equality-operator-), [!=](../../language-reference/operators/equality-operators.md#inequality-operator-), [\<](../../language-reference/operators/less-than-operator.md), [>](../../language-reference/operators/greater-than-operator.md), [\<=](../../language-reference/operators/less-than-equal-operator.md), [>=](../../language-reference/operators/greater-than-equal-operator.md)|Operadores de comparação podem ser sobrecarregados (consulte a observação após esta tabela).|
|[&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-)|Os operadores lógicos condicionais não podem ser sobrecarregados, mas são avaliados usando `&` e <code>&#124;</code>, que podem ser sobrecarregados.|
|[&#91;&#93;](../../language-reference/operators/index-operator.md)|O operador de indexação de matriz não pode ser sobrecarregado, mas você pode definir [indexadores](../indexers/index.md).|
|[(T)x](../../language-reference/operators/invocation-operator.md)|O operador de conversão não pode ser sobrecarregado, mas você pode definir novos operadores de conversão (consulte [explicit](../../language-reference/keywords/explicit.md) e [implicit](../../language-reference/keywords/implicit.md)).|
|[+=](../../language-reference/operators/addition-assignment-operator.md), [-=](../../language-reference/operators/subtraction-assignment-operator.md), [\*=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [/=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [%=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [&=](../../language-reference/operators/and-assignment-operator.md), [&#124;=](../../language-reference/operators/or-assignment-operator.md), [^=](../../language-reference/operators/xor-assignment-operator.md), [\<\<=](../../language-reference/operators/left-shift-assignment-operator.md), [>>=](../../language-reference/operators/right-shift-assignment-operator.md)|Operadores de atribuição não podem ser sobrecarregados explicitamente. No entanto, quando um operador binário está sobrecarregado, o operador de atribuição correspondente, se houver, também estará implicitamente sobrecarregado. Por exemplo, `+=` é avaliado usando `+`, que pode ser sobrecarregado.|
|[=](../../language-reference/operators/assignment-operator.md), [.](../../language-reference/operators/member-access-operator.md), [?:](../../language-reference/operators/conditional-operator.md), [??](../../language-reference/operators/null-coalescing-operator.md), [->](../../language-reference/operators/dereference-operator.md), [=>](../../language-reference/operators/lambda-operator.md), [f(x)](../../language-reference/operators/invocation-operator.md), [as](../../language-reference/keywords/as.md), [checked](../../language-reference/keywords/checked.md), [unchecked](../../language-reference/keywords/unchecked.md), [default](../../programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../language-reference/keywords/is.md), [new](../../language-reference/keywords/new.md), [sizeof](../../language-reference/keywords/sizeof.md), [typeof](../../language-reference/keywords/typeof.md)|Esses operadores não podem ser sobrecarregados.|

> [!NOTE]
> Os operadores de comparação, se sobrecarregados, devem ser sobrecarregados em pares. Ou seja, se `==` for sobrecarregado, `!=` também deve ser sobrecarregado. O contrário também é verdadeiro, no qual sobrecarregar `!=` requer uma sobrecarga para `==`. O mesmo vale para os operadores de comparação `<` e `>` e para `<=` e `>=`.

Para obter informações sobre como sobrecarregar um operador, consulte o artigo da palavra-chave [operador](../../language-reference/keywords/operator.md).

## <a name="see-also"></a>Consulte também

- [Guia de Programação em C#](../index.md)
- [Instruções, expressões e operadores](index.md)
- [Operadores](operators.md)
- [Operadores do C#](../../language-reference/operators/index.md)
- [Por que os operadores sobrecarregados sempre são estáticos em C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)
