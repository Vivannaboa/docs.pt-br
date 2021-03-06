---
title: 'Como: Associar aos resultados de uma consulta LINQ'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 5464ee9c59a7c99a83774a7535b9b3c422c1d2e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644405"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>Como: Associar aos resultados de uma consulta LINQ
Este exemplo demonstra como executar uma consulta LINQ e associar aos resultados.  
  
## <a name="example"></a>Exemplo  
 O seguinte exemplo cria duas caixas de listagem. A primeira caixa de listagem contém três itens de lista.  
  
 [!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 Selecionar um item na primeira caixa de listagem invoca o manipulador de eventos a seguir. Neste exemplo, `Tasks` é uma coleção de objetos `Task`. A classe `Task` tem uma propriedade chamada `Priority`. Esse manipulador de eventos executa uma consulta LINQ que retorna a coleção de `Task` objetos que têm o valor de prioridade selecionado e, em seguida, define que, como o <xref:System.Windows.FrameworkElement.DataContext%2A>:  
  
 [!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 A segunda caixa de listagem associado a essa coleção porque seu <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> valor é definido como `{Binding}`. Como resultado, ele exibe a coleção retornada (com base nas `myTaskTemplate` <xref:System.Windows.DataTemplate>).  
  
## <a name="see-also"></a>Consulte também

- [Disponibilizar dados para associação em XAML](how-to-make-data-available-for-binding-in-xaml.md)
- [Associar a uma coleção e exibir informações com base na seleção](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Novidades no WPF versão 4.5](../getting-started/whats-new.md)
- [Visão geral da vinculação de dados](data-binding-overview.md)
- [Tópicos de instruções](data-binding-how-to-topics.md)
