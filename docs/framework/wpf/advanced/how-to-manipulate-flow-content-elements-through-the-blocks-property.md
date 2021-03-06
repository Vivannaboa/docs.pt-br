---
title: 'Como: Manipular elementos de conteúdo de fluxo por meio da propriedade Blocks'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
ms.openlocfilehash: e0e1e1333a54946f3bdf474e353de0301eb42447
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942825"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a>Como: Manipular elementos de conteúdo de fluxo por meio da propriedade Blocks
Estes exemplos demonstram algumas das operações mais comuns que podem ser executadas em elementos de conteúdo de fluxo por meio da propriedade **Blocks**. Essa propriedade é usada para adicionar e remover itens de <xref:System.Windows.Documents.BlockCollection>. Elementos de conteúdo de fluxo com uma propriedade **Blocks** incluem:  
  
- <xref:System.Windows.Documents.Figure>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.ListItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.TableCell>  
  
 Esses exemplos, por acaso, usam <xref:System.Windows.Documents.Section> como o fluxo de elemento de conteúdo, mas essas técnicas são aplicáveis a todos os elementos que hospedam uma coleção de elementos de conteúdo de fluxo.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir cria um novo <xref:System.Windows.Documents.Section> e, em seguida, usa o **Add** para adicionar um novo parágrafo para o **seção** conteúdo.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir cria um novo <xref:System.Windows.Documents.Paragraph> elemento e o insere no início do <xref:System.Windows.Documents.Section>.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir obtém o número de nível superior <xref:System.Windows.Documents.Block> elementos contidos no <xref:System.Windows.Documents.Section>.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir exclui a última <xref:System.Windows.Documents.Block> elemento no <xref:System.Windows.Documents.Section>.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir limpa todo o conteúdo (<xref:System.Windows.Documents.Block> elementos) da <xref:System.Windows.Documents.Section>.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [Visão geral do documento de fluxo](flow-document-overview.md)
- [Manipular grupos de linhas de uma tabela por meio da propriedade RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [Manipular colunas de uma tabela por meio da propriedade Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Manipular grupos de linhas de uma tabela por meio da propriedade RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
