---
title: Aplicabilidade da transformação funcional (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 3b74e134-e19b-44bc-8d06-e26c48305040
ms.openlocfilehash: 7efeab82dafc284f64a950eb7f5e4a6ee3f2e73d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61689834"
---
# <a name="applicability-of-functional-transformation-visual-basic"></a>Aplicabilidade da transformação funcional (Visual Basic)
Transformações e puras são aplicáveis em uma variedade de situações.  
  
 A abordagem funcional de transformação é mais idealmente consultando e manipulando dados; estruturados portanto couber bem com as tecnologias LINQ. No entanto, a transformação funcional tem uma aplicabilidade muito maior do que o uso com LINQ. Alguns processam onde o foco principal está em transformar dados de um formulário para outro provavelmente deve ser considerado como um candidato para a transformação funcional.  
  
 Essa abordagem é aplicável a muitos problemas que não podem parecer à primeira vista para ser um candidato. Usado em conjunto ou separadamente com LINQ, a transformação funcional deve ser considerada para as seguintes áreas:  
  
- Documentos com base em XML. Os dados bem formado do dialeto de XML podem facilmente ser manipulados pela transformação funcional. Para obter mais informações, consulte [transformação funcional de XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md).  
  
- Outros formatos de arquivo estruturados. De Windows.ini arquivos aos documentos de texto sem formatação, a maioria dos arquivos têm qualquer estrutura que se empresta a análise e a transformação.  
  
- Os protocolos de streaming de dados. Os dados de codificação e nos dados de decodificação dos protocolos de comunicação geralmente podem ser representados por um funcional simples tornam-se.  
  
- Dados de RDBMS e de OODBMS. Os bases de dados relacionais e orientados a objeto, assim como XML, são estruturados fontes de dados amplamente usadas.  
  
- Matemático, estatística, e soluções de ciência. Esses campos tendem a manipular grandes conjuntos de dados para ajudar o usuário em visualizar, em estimar, ou realmente em resolver problemas não triviais.  
  
 Conforme descrito em [refatoração em funções puras (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md), usar funções puras é um exemplo de programação funcional. Em adicional a seus benefícios imediatos, usar funções puras fornece a experiência valiosa no pensamento sobre problemas de uma perspectiva funcional de transformação. Essa abordagem pode também ter o impacto principal no design do programa e da classe. Isso é especialmente verdadeiro quando um problema se empresta a uma solução de transformação de dados como descrito acima.  
  
 Embora eles sejam além do escopo deste tutorial, os projetos que são influenciados pela perspectiva funcional de transformação tendem a centralizar sobre processam mais do que em objetos como atores, e a solução resultante tendem a ser implementados como série de transformações em grande escala, em vez de alterações de estado individuais de objeto.  
  
 Novamente, lembre-se de que o Visual Basic suporta abordagens imperativas e funcionais, para que o melhor design para o seu aplicativo poderá incorporar os elementos de ambos.  
  
## <a name="see-also"></a>Consulte também

- [Introdução às transformações funcionais puras (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [Transformação funcional de XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)
- [Refatoração em funções puras (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
