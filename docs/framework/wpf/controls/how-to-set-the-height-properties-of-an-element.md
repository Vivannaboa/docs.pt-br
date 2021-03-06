---
title: 'Como: Definir as propriedades de altura de um elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: fb655630336c3b69afdc726a2e3c5a2cb8838667
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024411"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>Como: Definir as propriedades de altura de um elemento
## <a name="example"></a>Exemplo  
 Este exemplo mostra visualmente as diferenças no comportamento de renderização entre as quatro propriedades relacionadas à altura em [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 O <xref:System.Windows.FrameworkElement> classe expõe quatro propriedades que descrevem as características de altura de um elemento. Essas quatro propriedades podem conflitar e quando isso acontece, o valor que tem precedência é determinado da seguinte maneira: o <xref:System.Windows.FrameworkElement.MinHeight%2A> valor tem precedência sobre a <xref:System.Windows.FrameworkElement.MaxHeight%2A> valor, que por sua vez, tem precedência sobre o <xref:System.Windows.FrameworkElement.Height%2A> valor. Uma quarta propriedade, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, é somente leitura e relata a altura real determinada pelas interações com o processo de layout.  
  
 O seguinte [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] exemplos de desenham uma <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) como um filho de <xref:System.Windows.Controls.Canvas>. Você pode alterar as propriedades de altura de um <xref:System.Windows.Shapes.Rectangle> por meio de uma série de <xref:System.Windows.Controls.ListBox> elementos que representam os valores de propriedade de <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, e <xref:System.Windows.FrameworkElement.Height%2A>. Dessa forma, a precedência de cada propriedade é exibida visualmente.  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 Os seguintes exemplos de code-behind manipulam os eventos que o <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> aciona eventos. Cada manipulador pega a entrada do <xref:System.Windows.Controls.ListBox>, analisa o valor como um <xref:System.Double>e aplica o valor à propriedade de altura especificada. Os valores de altura também são convertidos em uma cadeia de caracteres e gravados em vários <xref:System.Windows.Controls.TextBlock> elementos (a definição desses elementos não é mostrada o XAML selecionado).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Para a amostra completa, consulte [Amostra de propriedades de altura](https://go.microsoft.com/fwlink/?LinkID=159993).  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [Definir as propriedades de largura de um elemento](how-to-set-the-width-properties-of-an-element.md)
- [Visão geral de painéis](panels-overview.md)
- [Exemplo de propriedades de altura](https://go.microsoft.com/fwlink/?LinkID=159993)
