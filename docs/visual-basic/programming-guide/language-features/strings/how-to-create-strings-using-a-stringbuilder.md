---
title: 'Como: Criar cadeias de caracteres usando StringBuilder no Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 00fefcc138164288d872cd339f165dc6ffc0131a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032117"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Como: Criar cadeias de caracteres usando StringBuilder no Visual Basic
Esse exemplo constrói uma cadeia de caracteres de várias cadeias menores utilizando o <xref:System.Text.StringBuilder> classe. O <xref:System.Text.StringBuilder> classe é mais eficiente do que o `&=` operador para concatenar várias cadeias de caracteres.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir cria uma instância da <xref:System.Text.StringBuilder> classe, anexa 1.000 cadeias de caracteres a essa instância e, em seguida, retorna sua representação de cadeia de caracteres.  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a>Consulte também

- [Uso da classe StringBuilder](../../../../standard/base-types/stringbuilder.md)
- [Operador &=](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Cadeias de Caracteres](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Criando novas cadeias de caracteres](../../../../standard/base-types/creating-new.md)
- [Manipulando cadeias de caracteres](../../../../standard/base-types/manipulating-strings.md)
