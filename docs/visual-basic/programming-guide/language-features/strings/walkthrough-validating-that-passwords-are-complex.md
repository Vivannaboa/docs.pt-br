---
title: Validação de complexidade de senhas (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 829d6485acdca22fbf10160c734e5c7f931dd855
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938249"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Passo a passo: Validando senhas complexas (Visual Basic)
Esse método verifica se há algumas características de senha forte e atualiza um parâmetro de cadeia de caracteres com informações sobre em quais verificações de senha falha.  
  
 Senhas podem ser usadas em um sistema seguro para autorizar um usuário. No entanto, as senhas devem ser difícil para usuários não autorizados estimem. Os invasores podem usar um *ataque de dicionário* programa, que itera por meio de todas as palavras em um dicionário (ou vários dicionários em linguagens diferentes) e teste se qualquer uma das palavras funciona como uma senha de usuário. Senhas fracas, como "Yankees" ou "Mustang" podem ser adivinhadas facilmente. Senhas mais fortes, como "? Você 'L1N3vaFiNdMeyeP@sSWerd! ", são muito menos provável de ser adivinhada. Um sistema protegido por senha deve garantir que os usuários escolham senhas fortes.  
  
 Uma senha forte é complexa (que contém uma mistura de caracteres maiusculos, minúsculos, numérico e especial) e não é uma palavra. Este exemplo demonstra como verificar a complexidade.  
  
## <a name="example"></a>Exemplo  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Chame esse método, passando a cadeia de caracteres que contém a senha.  
  
 Este exemplo requer:  
  
- Acesso aos membros do namespace <xref:System.Text.RegularExpressions>. Adicione uma instrução `Imports` se você não está qualificando totalmente os nomes de membros em seu código. Para obter mais informações, consulte [Instrução Imports (tipo e namespace .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Segurança  
 Se você estiver movendo a senha em uma rede, você precisa usar um método seguro para a transferência de dados. Para obter mais informações, consulte [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).
  
 Você pode melhorar a precisão do `ValidatePassword` função adicionando verificações de complexidade adicional:  
  
- Compare a senha e suas substrings com o nome do usuário, o identificador de usuário e um dicionário definido pelo aplicativo. Além disso, trate caracteres visualmente similares como equivalentes ao realizar as comparações. Por exemplo, trate as letras "l" e "e" como equivalentes aos numerais "1" e "3".  
  
- Se houver apenas um caractere maiusculo, certifique-se de não é o primeiro caractere do password.  
  
- Certifique-se de que os dois últimos caracteres da senha são caracteres de letras.  
  
- Não permita senhas em que todos os símbolos são inseridos na linha de parte superior do teclado.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Text.RegularExpressions.Regex>
- [Segurança de aplicativo Web ASP .NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))
