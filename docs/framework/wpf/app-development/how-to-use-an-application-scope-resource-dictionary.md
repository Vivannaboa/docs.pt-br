---
title: 'Como: Usar um dicionário de recursos no escopo do aplicativo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 589e28b3c05496e3fc17055b98240e389faed068
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007481"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Como: Usar um dicionário de recursos no escopo do aplicativo
Este exemplo mostra como definir e usar um dicionário de recursos personalizado de escopo do aplicativo.  
  
## <a name="example"></a>Exemplo  
 <xref:System.Windows.Application> expõe um armazenamento de escopo do aplicativo para recursos compartilhados: <xref:System.Windows.Application.Resources%2A>. Por padrão, o <xref:System.Windows.Application.Resources%2A> propriedade é inicializada com uma instância das <xref:System.Windows.ResourceDictionary> tipo. Usar essa instância ao obter e definir propriedades de escopo do aplicativo usando <xref:System.Windows.Application.Resources%2A>. Para obter mais informações, confira [Como: Obter e definir um recurso de escopo do aplicativo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).
  
 Se você tiver vários recursos que você definir usando <xref:System.Windows.Application.Resources%2A>, em vez disso, você pode usar um dicionário de recurso personalizado para armazenar esses recursos e definir <xref:System.Windows.Application.Resources%2A> com ele em vez disso. O exemplo a seguir mostra como declarar um dicionário de recurso personalizado usando XAML.
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Trocar dicionários de recursos inteiros usando <xref:System.Windows.Application.Resources%2A> permite dar suporte a temas de escopo do aplicativo, onde cada tema é encapsulado por um único dicionário de recursos. O exemplo a seguir mostra como definir o <xref:System.Windows.ResourceDictionary>.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 A seguir mostra como você pode obter os recursos de escopo do aplicativo de dicionário de recursos exposto pelo <xref:System.Windows.Application.Resources%2A> em XAML.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 O exemplo seguinte mostra como é possível também obter os recursos em código.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Há duas considerações a fazer ao usar <xref:System.Windows.Application.Resources%2A>. Primeiro, o dicionário *chave* é um objeto, então você deve usar exatamente a mesma instância de objeto quando ambos definem e obtêm um valor da propriedade. (Note que a chave faz distinção entre maiúsculas e minúsculas ao usar uma cadeia de caracteres.) Segundo, o dicionário *valor* é um objeto, então você precisará converter o valor para o tipo desejado ao obter um valor de propriedade.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [Recursos XAML](../advanced/xaml-resources.md)
- [Dicionários de recursos mesclados](../advanced/merged-resource-dictionaries.md)
