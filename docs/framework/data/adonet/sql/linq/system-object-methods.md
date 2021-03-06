---
title: Métodos de System.Object
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: 3a52f081f1c0c6e6c5218550009c736d0ed60514
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917654"
---
# <a name="systemobject-methods"></a>Métodos de System.Object
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] suporta as seguintes <xref:System.Object> métodos.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] não oferece suporte aos seguintes métodos de <xref:System.Object> .  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> para tipos binários como `BINARY`, `VARBINARY`, `IMAGE`, e `TIMESTAMP`.||  
  
## <a name="differences-from-net"></a>Diferenças do .NET  
 A saída de <xref:System.Object.ToString?displayProperty=nameWithType> para o tipo double usando SQL `CONVERT`(nvarchar (30), @x, 2) no SQL. O SQL usa sempre 16 dígitos e notação científica nesse caso (por exemplo, “0.000000000000000e+000” para 0). Como resultado, a conversão de <xref:System.Object.ToString?displayProperty=nameWithType> não gerencia a mesma cadeia de caracteres que <xref:System.Convert.ToString%2A?displayProperty=nameWithType> no.NET Framework.  
  
## <a name="see-also"></a>Consulte também

- [Funções e tipos de dados](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
