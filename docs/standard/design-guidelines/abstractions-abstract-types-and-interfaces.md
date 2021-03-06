---
title: Abstrações (tipos e interfaces abstratos)
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
author: KrzysztofCwalina
ms.openlocfilehash: fcf566c24677630fdbb1fcd0eb7628f830b3be2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789214"
---
# <a name="abstractions-abstract-types-and-interfaces"></a>Abstrações (tipos e interfaces abstratos)
Uma abstração é um tipo que descreve um contrato, mas não fornece uma implementação completa do contrato. Abstrações geralmente são implementadas como classes abstratas ou interfaces, e entram com um conjunto bem definido de documentação de referência que descreve a semântica necessária dos tipos de implementação do contrato. Algumas das abstrações mais importantes no .NET Framework incluem <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, e <xref:System.Object>.  
  
 Você pode estender estruturas implementando um tipo concreto que dá suporte ao contrato de uma abstração e usando esse tipo concreto com framework APIs consumo (operando em) a abstração.  
  
 Uma abstração de significativa e úteis que é capaz de suportar o teste de tempo é muito difícil de design. A dificuldade principal é obter o conjunto certo de membros, não há mais e menos não. Se uma abstração tem muitos membros, fica difícil ou até mesmo impossível implementar. Se ela tiver muito poucos membros para a funcionalidade prometido, se tornará inútil em muitos cenários interessantes.  
  
 Número excessivo de abstrações em uma estrutura também afetam de usabilidade do framework. Geralmente é muito difícil de entender uma abstração sem compreender como ele se adapta a imagem maior de APIs operando com a abstração e as implementações concretas. Além disso, os nomes das abstrações e seus membros são necessariamente abstratos, que muitas vezes os torna confuso e não-receptiva sem primeiro compreender o contexto mais amplo de uso.  
  
 No entanto, as abstrações fornecem extensibilidade extremamente poderosa que geralmente não podem corresponder a outros mecanismos de extensibilidade. Eles são a essência de muitos padrões de arquitetura, como plug-ins, inversão de controle (IoC), pipelines e assim por diante. Eles também são extremamente importantes para a capacidade de teste de estruturas. Boa abstrações tornam possível criar um stub dependências pesadas para fins de teste de unidade. Em resumo, as abstrações são responsáveis pela riqueza mais ansiada das estruturas modernas orientadas a objeto.  
  
 **X DO NOT** fornecem abstrações, a menos que eles são testados com o desenvolvimento de várias implementações concretas e APIs, as abstrações de consumo.  
  
 **✓ DO** escolha cuidadosamente entre uma classe abstrata e uma interface ao projetar uma abstração.  
  
 **✓ CONSIDER** fornecendo testes de referência para implementações concretas das abstrações. Esses testes devem permitir que os usuários testar se suas implementações implementam corretamente o contrato.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*  
  
 *Reimpresso com permissão da Pearson Education, Inc. de [as diretrizes de Design do Framework: As convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicados 22 de outubro de 2008 pela Addison-Wesley Professional, como parte da série de desenvolvimento do Microsoft Windows.*  
  
## <a name="see-also"></a>Consulte também

- [Diretrizes de design do Framework](../../../docs/standard/design-guidelines/index.md)
- [Designer voltado para extensibilidade](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
