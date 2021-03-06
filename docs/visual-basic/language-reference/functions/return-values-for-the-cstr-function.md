---
title: Retornar valores para a função CStr (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: 3653194c7e48533e664ac7513ca7f4f48d1c69f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801524"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Retornar valores para a função CStr (Visual Basic)
A tabela a seguir descreve os valores retornados pela `CStr` para tipos de dados diferentes de `expression`.  
  
|Se `expression` é do tipo|Retornos de `CStr`|  
|-----------------------------|--------------------|  
|[Tipo de Dados Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Uma cadeia de caracteres que contém "True" ou "False".|  
|[Tipo de Dados de Data](../../../visual-basic/language-reference/data-types/date-data-type.md)|Uma cadeia de caracteres que contém um `Date` valor (data e hora) em formato de data abreviada do seu sistema.|  
|[Tipos de Dados Numéricos](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Uma cadeia de caracteres que representa o número.|  
  
## <a name="cstr-and-date"></a>Data e CStr  
 O `Date` tipo sempre contém informações de data e hora. Para fins de conversão de tipo, o Visual Basic considera 1/1/0001 (1 de janeiro do ano 1) como um *valor neutro* para a data e 00:00:00 (meia-noite) ser um valor neutro para a hora. `CStr` não inclui valores neutros na cadeia de caracteres resultante. Por exemplo, se você converter `#January 1, 0001 9:30:00#` como uma cadeia de caracteres, o resultado será "9:30:00 AM"; as informações de data são suprimidas. No entanto, as informações de data ainda estão presentes no original `Date` de valor e pode ser recuperada com funções como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
> [!NOTE]
>  O `CStr` função executa a conversão com base nas configurações de cultura atual para o aplicativo. Para obter a representação de cadeia de caracteres de um número em uma cultura específica, use o número `ToString(IFormatProvider)` método. Por exemplo, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> ao converter um valor do tipo `Double` para um `String`.  
  
## <a name="see-also"></a>Consulte também

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [Funções de Conversão do Tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Tipo de Dados Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Tipo de Dados de Data](../../../visual-basic/language-reference/data-types/date-data-type.md)
