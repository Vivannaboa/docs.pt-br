---
title: 'Como: Exibir Ícones do Controle ListView do Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 8e4ae744eecbe894767114179dd63651828b191b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013433"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>Como: Exibir Ícones do Controle ListView do Windows Forms
Os formulários do Windows <xref:System.Windows.Forms.ListView> controle pode exibir ícones das três listas de imagens. Os modos de exibição de lista, detalhes e SmallIcon exibem imagens da lista de imagens especificada no <xref:System.Windows.Forms.ListView.SmallImageList%2A> propriedade. O modo de exibição LargeIcon exibe imagens da lista de imagens especificada no <xref:System.Windows.Forms.ListView.LargeImageList%2A> propriedade. Uma exibição de lista também pode exibir um conjunto adicional de ícones, definido no <xref:System.Windows.Forms.ListView.StateImageList%2A> propriedade, ao lado de ícones grandes ou pequenos. Para obter mais informações sobre listas de imagens, consulte [componente ImageList](imagelist-component-windows-forms.md) e [como: Adicionar ou remover imagens com o Windows Forms componente ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
### <a name="to-display-images-in-a-list-view"></a>Para exibir imagens em uma exibição de lista  
  
1. Defina a propriedade apropriada —<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, ou <xref:System.Windows.Forms.ListView.StateImageList%2A>— ao existente <xref:System.Windows.Forms.ImageList> componente que você deseja usar.  
  
     Essas propriedades podem ser definidas no designer com a janela Propriedades ou no código.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. Defina as <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> ou <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> propriedade para cada item de lista que tem um ícone associado.  
  
     Essas propriedades podem ser definidas no código ou no **Editor de coleção ListViewItem**. Para abrir o **Editor de coleção ListViewItem**, clique no botão de reticências (![captura de tela de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) ao lado de <xref:System.Windows.Forms.ListView.Items%2A>propriedade de **propriedades** janela.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>Consulte também

- [Visão geral do controle ListView](listview-control-overview-windows-forms.md)
- [Como: Adicionar e remover itens com o controle ListView do Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Como: Adicionar colunas para o controle ListView do Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Como: Adicionar informações personalizadas a um controle TreeView ou ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Componente ImageList](imagelist-component-windows-forms.md)
