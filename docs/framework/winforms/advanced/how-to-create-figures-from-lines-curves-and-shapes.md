---
title: 'Como: criar figuras usando linhas, curvas e formas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: eeaf478375e08734b20d83b6f3c8030732495013
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937690"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>Como: criar figuras usando linhas, curvas e formas
Para criar uma figura, construa uma <xref:System.Drawing.Drawing2D.GraphicsPath>e, em seguida, chamar métodos, como <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, para adicionar primitivos ao caminho.  
  
## <a name="example"></a>Exemplo  
 Os exemplos de código a seguir criam caminhos que têm figuras:  
  
- O primeiro exemplo cria um caminho que contém uma figura única. A figura consiste em um único arco. O arco tem um ângulo de flecha de -180 graus, no sentido anti-horário no sistema de coordenadas padrão.  
  
- O segundo exemplo cria um caminho que contém duas figuras. A primeira figura é um arco seguido por uma linha. A segunda figura é uma linha seguida por uma curva seguida por uma linha. A primeira figura foi deixada aberta e a segunda figura está fechada.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Os exemplos anteriores são projetados para uso com o Windows Forms e exigem <xref:System.Windows.Forms.PaintEventArgs> `e`, que é um parâmetro do <xref:System.Windows.Forms.Control.Paint> manipulador de eventos.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Construindo e desenhando demarcadores](constructing-and-drawing-paths.md)
- [Usando uma caneta para desenhar linhas e formas](using-a-pen-to-draw-lines-and-shapes.md)
