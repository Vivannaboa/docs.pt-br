---
title: 'Como: Obter ou definir propriedades de posicionamento da tela'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 06508e1198736ccb1cbda41641dff4bc634ef82b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910475"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a>Como: Obter ou definir propriedades de posicionamento da tela
Este exemplo mostra como usar os métodos de posicionamento a <xref:System.Windows.Controls.Canvas> elemento para posicionar conteúdo filho. Este exemplo usa conteúdo em um <xref:System.Windows.Controls.ListBoxItem> para representar valores de posicionamento e converte os valores em instâncias de <xref:System.Double>, que é um argumento requerido para posicionamento. Os valores são, em seguida, convertidos de volta em cadeias de caracteres e exibidos como texto em uma <xref:System.Windows.Controls.TextBlock> elemento usando o <xref:System.Windows.Controls.Canvas.GetLeft%2A> método.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir cria uma <xref:System.Windows.Controls.ListBox> elemento que tem onze selecionável <xref:System.Windows.Controls.ListBoxItem> elementos. O <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> gatilhos de evento o `ChangeLeft` método personalizado, que o bloco de código subsequente define.  
  
 Cada <xref:System.Windows.Controls.ListBoxItem> representa uma <xref:System.Double> valor, que é um dos argumentos que o <xref:System.Windows.Controls.Canvas.SetLeft%2A> método <xref:System.Windows.Controls.Canvas> aceita. Para usar um <xref:System.Windows.Controls.ListBoxItem> para representar uma instância do <xref:System.Double>, você deve primeiro converter o <xref:System.Windows.Controls.ListBoxItem> para o tipo de dados correto.  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 Quando um usuário altera a <xref:System.Windows.Controls.ListBox> seleção, ele invoca o `ChangeLeft` método personalizado. Esse método passa o <xref:System.Windows.Controls.ListBoxItem> para um <xref:System.Windows.LengthConverter> objeto, que converte o <xref:System.Windows.Controls.ContentControl.Content%2A> de uma <xref:System.Windows.Controls.ListBoxItem> a uma instância do <xref:System.Double> (Observe que esse valor já foi convertido em um <xref:System.String> usando o <xref:System.Windows.Controls.Control.ToString%2A> método). Esse valor é passado, em seguida, volta para o <xref:System.Windows.Controls.Canvas.SetLeft%2A> e <xref:System.Windows.Controls.Canvas.GetLeft%2A> métodos da <xref:System.Windows.Controls.Canvas> para alterar a posição do `text1` objeto.  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [Visão geral de painéis](panels-overview.md)
