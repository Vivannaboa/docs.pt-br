---
title: LIMITAR (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: b267e97860a2cb071b857224455f01b73115c72d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760669"
---
# <a name="limit-entity-sql"></a>LIMITAR (Entity SQL)
A paginação física pode ser executada usando a subcláusula LIMIT em uma ORDER BY. LIMIT não pode ser usada separadamente da cláusula ORDER BY.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a>Arguments  
 `n`  
 O número de itens que serão selecionados.  
  
 Se uma subcláusula de expressão LIMIT estiver presente em uma cláusula ORDER BY, a consulta será classificada de acordo com a especificação de classificação e o número de linhas resultante será restrito pela expressão LIMIT. Por exemplo, LIMIT 5 restringirá o conjunto de resultados a 5 instâncias ou linhas. LIMIT é funcionalmente equivalente à TOP com a exceção de que a LIMIT requer que a cláusula ORDER BY esteja presente. SKIP e LIMIT podem ser usadas independentemente junto com a cláusula ORDER BY.  
  
> [!NOTE]
>  Uma consulta Entity SQL será considerada inválida se o modificador TOP e a subcláusula SKIP estiverem presentes na mesma expressão de consulta. A consulta deve ser reescrita alterando a expressão TOP para uma expressão LIMIT.  
  
## <a name="example"></a>Exemplo  
 A seguinte consulta Entity SQL usa o operador ORDER BY com LIMIT para especificar ordem de classificação usada em objetos retornados em uma instrução SELECT. A consulta é baseada no modelo de vendas AdventureWorks. Para compilar e executar essa consulta, siga estas etapas:  
  
1. Siga o procedimento em [como: Executar uma consulta que retorna resultados Structuraltype](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passe a consulta a seguir como um argumento para o método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a>Consulte também

- [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [Como: Paginar os resultados da consulta](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
- [Paginação](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
