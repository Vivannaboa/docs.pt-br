---
title: Elementos gráficos e desenho no Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 08f87436ade62bb54295b012a1c24dc177ea9667
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938171"
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Elementos gráficos e desenho no Windows Forms
O Common Language Runtime usa uma implementação avançada do Windows Graphics Device Interface ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) chamado [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Com [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], é possível criar gráficos, desenhar texto e manipular imagens gráficas como objetos. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] foi projetado para oferecer desempenho e facilidade de uso. Você pode usar [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para renderizar imagens gráficas em controles e nos Windows Forms. Embora não seja possível usar [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] diretamente no Web Forms, é possível exibir imagens gráficas por meio do controle de servidor Web de Imagem.  
  
 Nesta seção, você encontrará tópicos que apresentam os conceitos básicos da programação do [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Embora não se destina a ser uma referência abrangente, esta seção inclui informações sobre o <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, e <xref:System.Drawing.Color> objetos e explica como executar tarefas como desenhar formas, desenhando texto, ou exibindo imagens. Para obter mais informações, consulte [referência GDI+](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).  
  
 Se você deseja começar imediatamente, consulte [Introdução à programação de elementos gráficos](getting-started-with-graphics-programming.md). Ele apresenta tópicos sobre como usar código para desenhar linhas, formas, texto e muito mais em Windows Forms.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Visão geral de elementos gráficos](graphics-overview-windows-forms.md)  
 Fornece uma introdução a classes gerenciadas relacionadas a elementos gráficos.  
  
 [Sobre o Código Gerenciado no GDI+](about-gdi-managed-code.md)  
 Fornece informações sobre as classes [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] gerenciadas.  
  
 [Usando Classes de Elementos Gráficos Gerenciadas](using-managed-graphics-classes.md)  
 Demonstra como completar uma variedade de tarefas usando as classes gerenciadas [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
## <a name="reference"></a>Referência  
 <xref:System.Drawing>  
 Fornece acesso à funcionalidade básica [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] de elementos gráficos.  
  
 <xref:System.Drawing.Drawing2D>  
 Fornece funcionalidade avançada bidimensional e de gráfico vetorial.  
  
 <xref:System.Drawing.Imaging>  
 Fornece funcionalidade avançada de imagens [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 <xref:System.Drawing.Text>  
 Fornece funcionalidade avançada de tipografia [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. As classes nesse namespace podem ser usadas para criar e usar coleções de fontes.  
  
 <xref:System.Drawing.Printing>  
 Fornece funcionalidade de impressão.  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Pintura e renderização de controle personalizado](../controls/custom-control-painting-and-rendering.md)  
 Detalhes sobre como fornecer código para pintar controles.
