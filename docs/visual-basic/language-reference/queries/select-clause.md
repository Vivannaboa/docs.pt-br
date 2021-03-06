---
title: Cláusula Select (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: 367d810c2358963bfe2f092a390443eccdc66941
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945256"
---
# <a name="select-clause-visual-basic"></a>Cláusula Select (Visual Basic)
Define o resultado de uma consulta.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Partes  
 `var1`  
 Opcional. Um alias que pode ser usado para referenciar os resultados da expressão de coluna.  
  
 `fieldName1`  
 Necessário. O nome do campo a ser retornado no resultado da consulta.  
  
## <a name="remarks"></a>Comentários  
 Você pode usar o `Select` cláusula para definir os resultados retornados de uma consulta. Isso permite que você definir os membros de um novo tipo anônimo que é criado por uma consulta, ou os membros de um tipo nomeado que é retornado por uma consulta de destino. O `Select` cláusula não é necessária para uma consulta. Se nenhum `Select` cláusula for especificada, a consulta retornará um tipo com base em todos os membros das variáveis de intervalo identificadas no escopo atual. Para obter mais informações, consulte [Tipos anônimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Quando uma consulta cria um tipo nomeado, ela retornará um resultado do tipo <xref:System.Collections.Generic.IEnumerable%601> onde `T` é do tipo criado.  
  
 O `Select` cláusula pode referenciar qualquer variável no escopo atual. Isso inclui variáveis de intervalo identificadas na `From` cláusula (ou `From` cláusulas). Ele também inclui quaisquer variáveis novas criadas com um alias, o `Aggregate`, `Let`, `Group By`, ou `Group Join` cláusulas ou variáveis do anterior `Select` cláusula na expressão de consulta. O `Select` cláusula também pode incluir valores estáticos. Por exemplo, o exemplo de código a seguir mostra uma expressão de consulta em que o `Select` cláusula define o resultado da consulta como um novo tipo anônimo com quatro membros: `ProductName`, `Price`, `Discount`, e `DiscountedPrice`. O `ProductName` e `Price` os valores de membro são tirados da variável de intervalo do produto que é definido no `From` cláusula. O `DiscountedPrice` valor do membro é calculado no `Let` cláusula. O `Discount` membro é um valor estático.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 O `Select` cláusula introduz um novo conjunto de variáveis de intervalo para cláusulas de consulta subsequentes, e as variáveis de intervalo anterior não estão mais no escopo. A última `Select` cláusula em uma expressão de consulta determina o valor de retorno da consulta. Por exemplo, a consulta a seguir retorna a empresa nome e a ordem de ID para cada pedido de cliente para o qual o total exceder 500. A primeira `Select` cláusula identifica as variáveis de intervalo para o `Where` cláusula e a segunda `Select` cláusula. O segundo `Select` cláusula identifica os valores retornados pela consulta como um novo tipo anônimo.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Se o `Select` cláusula identifica um único item para retornar, a expressão de consulta retorna uma coleção do tipo de item único. Se o `Select` cláusula identifica vários itens para retornar, a expressão de consulta retorna uma coleção de um novo tipo anônimo, com base nos itens selecionados. Por exemplo, duas consultas a seguir retornam coleções de dois tipos diferentes com base no `Select` cláusula. A primeira consulta retorna uma coleção de nomes de empresa como cadeias de caracteres. A segunda consulta retorna uma coleção de `Customer` objetos preenchidos com os nomes de empresa e informações de endereço.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Exemplo  
 A seguinte consulta de expressão usa uma `From` cláusula para declarar uma variável de intervalo `cust` para o `customers` coleção. O `Select` cláusula seleciona o nome do cliente e o valor de ID e preenche o `CompanyName` e `CustomerID` colunas da nova variável de intervalo. O `For Each` instrução faz um loop sobre cada objeto retornado e exibe as `CompanyName` e `CustomerID` colunas para cada registro.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>Consulte também

- [Introdução ao LINQ no Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Cláusula From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Cláusula Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Cláusula Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Tipos Anônimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
