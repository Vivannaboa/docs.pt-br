---
title: Objetos XName e XNamespace Atomizados (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
ms.openlocfilehash: fe0c4429c89e0028b3b012c87684bd14048de27a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61951925"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a>Objetos XName e XNamespace Atomizados (LINQ to XML) (Visual Basic)

Os objetos <xref:System.Xml.Linq.XName> e <xref:System.Xml.Linq.XNamespace> são *atomizados*, isto é, se eles contêm o mesmo nome qualificado, referem-se ao mesmo objeto. Isso resulta em benefícios de desempenho para consultas: Quando você compara dois nomes atomizados quanto à igualdade, a linguagem intermediária subjacente só precisa determinar se as duas referências apontam para o mesmo objeto. O código subjacente não tem que fazer as comparações de cadeias de caracteres, que poderiam demoradas.

## <a name="atomization-semantics"></a>Semântica de atomização

A atomização significa que se dois objetos de <xref:System.Xml.Linq.XName> têm o mesmo nome local, e estão no mesmo namespace, compartilham a mesma instância. Da mesma forma, se dois objetos de <xref:System.Xml.Linq.XNamespace> têm o mesmo URI de namespace, compartilham a mesma instância.

Para que uma classe permite objetos atomizados, o construtor para a classe deve ser particular, não público. Isso ocorre porque se foi o construtor público, você pode criar um objeto não atomizado. As classes de <xref:System.Xml.Linq.XName> e de <xref:System.Xml.Linq.XNamespace> implementam um operador de conversão implícita para converter uma cadeia de caracteres em <xref:System.Xml.Linq.XName> ou em <xref:System.Xml.Linq.XNamespace>. Isso é como você obtém uma instância desses objetos. Você não pode obter uma instância usando um construtor, porque o construtor é inacessível.

<xref:System.Xml.Linq.XName> e <xref:System.Xml.Linq.XNamespace> também implementam os operadores de igualdade e desigualdade de, para determinar se dois objetos que estão sendo comparados são referências para a mesma instância.

## <a name="example"></a>Exemplo

O código a seguir cria alguns objetos de <xref:System.Xml.Linq.XElement> e demonstrar-los que os nomes idênticos compartilham a mesma instância.

```vb
Dim r1 As New XElement("Root", "data1")
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")

If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")
Else
    Console.WriteLine("Different")
End If

Dim n As XName = "Root"

If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")
Else
    Console.WriteLine("Different")
End If
```

Este exemplo gera a seguinte saída:

```
r1 and r2 have names that refer to the same instance.
The name of r1 and the name in 'n' refer to the same instance.
```

Como mencionado anteriormente, a vantagem de objetos atomizados é que quando você usa um dos métodos do eixo que recebem <xref:System.Xml.Linq.XName> como um parâmetro, o método do eixo só precisa determinar que dois nomes referenciam a mesma instância para selecionar os elementos desejados.

O exemplo a seguir <xref:System.Xml.Linq.XName> passa a chamada de método <xref:System.Xml.Linq.XContainer.Descendants%2A> , que tem em melhor desempenho devido ao padrão de atomização.

```vb
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))

Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e

For Each z As var In query
    Console.WriteLine(z)
Next
```

Este exemplo gera a seguinte saída:

```xml
<C1>1</C1>
<C1>1</C1>
```

## <a name="see-also"></a>Consulte também

- [Desempenho (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
