---
title: O atributo '<attributename>' não pode ser aplicado várias vezes
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: da4a766e2617308cb33b9673a88db9e7a954152a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935311"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>Atributo '\<attributename >' não pode ser aplicado várias vezes
O atributo pode ser aplicado somente uma vez. O `AttributeUsage` atributo determina se um atributo pode ser aplicado mais de uma vez.  
  
 **ID do erro:** BC30663  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
1. Verifique se que o atributo é aplicado somente uma vez.  
  
2. Se você estiver usando atributos personalizados que você desenvolveu, considere alterar seus `AttributeUsage` atributo para permitir que vários usos de atributo, assim como acontece com o exemplo a seguir.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Consulte também

- <xref:System.AttributeUsageAttribute>
- [Criando Atributos Personalizados](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
