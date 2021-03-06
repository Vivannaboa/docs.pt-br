---
title: Tipos aninhados
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
author: KrzysztofCwalina
ms.openlocfilehash: 22c14d05105154ff642cb8a44eda8e7c5d0575e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756865"
---
# <a name="nested-types"></a>Tipos aninhados
Um tipo aninhado é um tipo definido dentro do escopo de outro tipo, que é chamado de tipo de delimitador. Um tipo aninhado tem acesso a todos os membros do seu tipo delimitador. Por exemplo, ele tem acesso a campos privados, definidos no tipo delimitador e protegidos campos definidos em todos os ascendentes do tipo delimitador.  
  
 Em geral, os tipos aninhados devem ser usados com moderação. Há vários motivos para isso. Alguns desenvolvedores não estão totalmente familiarizados com o conceito. Esses desenvolvedores podem, por exemplo, ter problemas com a sintaxe de declaração de variáveis de tipos aninhados. Tipos aninhados são também muito estreitamente ligados aos seus tipos delimitadores e como tal, não são adequados para serem tipos de uso geral.  
  
 Tipos aninhados são mais adequados para modelar os detalhes de implementação de seus tipos delimitadores. O usuário final deve ter raramente declarar variáveis de um tipo aninhado e quase nunca deve ter que instanciar explicitamente os tipos aninhados. Por exemplo, o enumerador de uma coleção pode ser um tipo aninhado dessa coleção. Enumeradores normalmente são instanciados por meio de seu tipo delimitador e, como muitas linguagens oferecem suporte a instrução foreach, variáveis de enumerador raramente tem que ser declarado pelo usuário final.  
  
 **✓ DO** usar tipos aninhados quando a relação entre o tipo aninhado e seu tipo externo é tal que a semântica de acessibilidade de membros é desejável.  
  
 **X DO NOT** tipos aninhados públicos em uso como um agrupamento lógico construir; use namespaces para isso.  
  
 **X AVOID** exposto publicamente tipos aninhados. A única exceção a isso é se as variáveis do tipo aninhado precisam ser declarada somente em cenários raros, como subclasses ou em outros cenários de personalização avançada.  
  
 **X DO NOT** usar tipos aninhados, se o tipo é provavelmente serão mencionados fora do tipo recipiente.  
  
 Por exemplo, uma enumeração passada para um método definido em uma classe não deve ser definida como um tipo aninhado na classe.  
  
 **X DO NOT** usar tipos aninhados se eles precisam ser instanciado pelo código do cliente.  Se um tipo tem um construtor público, ele provavelmente não deve ser aninhado.  
  
 Se um tipo pode ser instanciado, parece que indicam o tipo tem um lugar no framework por conta própria (você pode criá-lo, trabalhar com ele e destruí-lo sem nunca, usando o tipo externo) e, portanto, não devem ser aninhados. Tipos internos não devem ser reutilizados amplamente fora do tipo externo sem qualquer relação qualquer que seja o tipo externo.  
  
 **X DO NOT** definir um tipo aninhado como um membro de uma interface. Muitas linguagens não dão suporte a um constructo.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*  
  
 *Reimpresso com permissão da Pearson Education, Inc. de [as diretrizes de Design do Framework: As convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicados 22 de outubro de 2008 pela Addison-Wesley Professional, como parte da série de desenvolvimento do Microsoft Windows.*  
  
## <a name="see-also"></a>Consulte também

- [Diretrizes de Design de tipo](../../../docs/standard/design-guidelines/type.md)
- [Diretrizes de design do Framework](../../../docs/standard/design-guidelines/index.md)
