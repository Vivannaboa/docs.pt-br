---
title: 'Como: Inclinar um elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 47f671f493e7b379c36f9bf4b50ec9d185d10b8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61804047"
---
# <a name="how-to-skew-an-element"></a>Como: Inclinar um elemento
Este exemplo mostra como usar um <xref:System.Windows.Media.SkewTransform> para inclinar um elemento. Uma distorção, também conhecida como cisalhamento, é uma transformação que alonga o espaço de coordenadas de uma maneira não uniforme. Um uso típico de um <xref:System.Windows.Media.SkewTransform> é para simular [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] profundidade em [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] objetos.  
  
 Use o <xref:System.Windows.Media.SkewTransform.CenterX%2A> e <xref:System.Windows.Media.SkewTransform.CenterY%2A> as propriedades para especificar o centro do ponto do <xref:System.Windows.Media.SkewTransform>.  
  
 Use o <xref:System.Windows.Media.SkewTransform.AngleX%2A> e <xref:System.Windows.Media.SkewTransform.AngleY%2A> propriedades para especificar o ângulo de inclinação do eixo x e eixo y e para distorcer o sistema de coordenadas atual ao longo desses eixos.  
  
 Para prever o efeito de uma transformação de distorção, considere que <xref:System.Windows.Media.SkewTransform.AngleX%2A> distorce os valores do eixo x em relação ao sistema de coordenadas original. Portanto, para um <xref:System.Windows.Media.SkewTransform.AngleX%2A> de 30, o eixo y gira 30 graus pela origem e distorce os valores em x-em 30 graus a partir dessa origem. Da mesma forma, um <xref:System.Windows.Media.SkewTransform.AngleY%2A> de 30 distorce os valores y da forma em 30 graus da origem. Observe que este não é o mesmo efeito que mover o sistema de coordenadas em 30 graus em x ou y.  
  
 O exemplo a seguir aplica uma distorção horizontal de 45 graus para um <xref:System.Windows.Shapes.Rectangle> de um ponto central (0,0).  
  
## <a name="example"></a>Exemplo  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 O exemplo a seguir aplica uma distorção horizontal de 45 graus para um <xref:System.Windows.Shapes.Rectangle> de um ponto central (25,25).  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 O exemplo a seguir aplica uma distorção vertical de 45 graus para um <xref:System.Windows.Shapes.Rectangle> de um ponto central (25,25).  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 A ilustração a seguir mostra as diferentes distorções usadas neste exemplo.  
  
 ![Exemplos SkewTransform](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
Três exemplos ilustrativos de SkewTransform  
  
 Para obter o exemplo completo, consulte [Amostras de Transformação 2D](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [Visão geral de transformações](transforms-overview.md)
- [Tópicos de instruções](transformations-how-to-topics.md)
