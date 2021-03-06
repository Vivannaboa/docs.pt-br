---
title: <seealso> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 0df999ef502bf61bdfb65cb472947b93efded36e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940771"
---
# <a name="seealso-visual-basic"></a>\<seealso > (Visual Basic)
Especifica um link que aparece na seção Consulte também.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a>Parâmetros  
 `member`  
 Uma referência a um membro ou campo disponível para ser chamado do ambiente de compilação atual. O compilador verifica se o elemento de código fornecido existe e passa `member` para o nome de elemento no XML de saída. `member` deve ser exibido entre aspas duplas (" ").  
  
## <a name="remarks"></a>Comentários  
 Use o `<seealso>` marca para especificar o texto que você deseja que apareça em uma seção Consulte também. Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) para especificar um link de dentro do texto.  
  
 Compile com [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para processar comentários de documentação em um arquivo.  
  
## <a name="example"></a>Exemplo  
 Este exemplo usa o `<seealso>` marcar na `DoesRecordExist` seção para se referir a comentários de `UpdateRecord` método.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Consulte também

- [Marcações de Comentário XML](../../../visual-basic/language-reference/xmldoc/index.md)
