---
title: 'Como: Como identificar erros e exceções que ocorram na associação de dados'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
ms.openlocfilehash: 709db2a98074e3322adad8b1275b3c4418c14636
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941265"
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a>Como: Como identificar erros e exceções que ocorram na associação de dados
Muitas vezes, erros e exceções ocorrem nos objetos de negócios subjacentes quando você os associa aos controles. Você pode interceptar esses erros e exceções e, em seguida, recuperar ou passar as informações de erro para o usuário manipulando o <xref:System.Windows.Forms.Binding.BindingComplete> eventos para um determinado <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource>, ou <xref:System.Windows.Forms.CurrencyManager> componente.  
  
## <a name="example"></a>Exemplo  
 Este exemplo de código demonstra como tratar erros e exceções que ocorrem durante uma operação de associação de dados. Ele demonstra como interceptar erros manipulando o <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> eventos do <xref:System.Windows.Forms.Binding> objetos. Para interceptar erros e exceções ao manipular esse evento, você deve habilitar a formatação para a associação. Você pode habilitar a formatação quando a associação for construída ou adicionada à coleção de associação ou definindo o <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> propriedade para `true`.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 Quando o código está em execução e uma cadeia de caracteres vazia é inserida para o nome da peça ou um valor menor que 100 é inserido para o número de peça, uma caixa de mensagem será exibida. Este é um resultado de tratamento de <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> evento para essas associações de caixa de texto.  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
- Referências aos assemblies System, System.Drawing e System.Windows.Forms.  
  
 Para obter informações sobre como compilar este exemplo da linha de comando para o Visual Basic ou Visual c#, consulte [compilando da linha de comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [criação de linha de comando com csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Você também pode criar este exemplo no Visual Studio colando o código em um novo projeto.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>
- [Componente BindingSource](bindingsource-component.md)
