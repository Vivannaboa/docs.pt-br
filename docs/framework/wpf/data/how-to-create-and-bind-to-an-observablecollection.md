---
title: 'Como: Criar e associar a um ObservableCollection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], ObservableCollection class
- notifications [WPF]
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
ms.openlocfilehash: 45f8b097bfdb8d3d7994e53ea05146aa6de0fc21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020914"
---
# <a name="how-to-create-and-bind-to-an-observablecollection"></a>Como: Criar e associar a um ObservableCollection
Este exemplo mostra como criar e associar a uma coleção que deriva de <xref:System.Collections.ObjectModel.ObservableCollection%601> classe, que é uma classe de coleção que oferece notificações quando itens são adicionados ou removidos.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra a implementação de uma coleção do `NameList`:  
  
```csharp  
public class NameList : ObservableCollection<PersonName>  
{  
    public NameList() : base()  
    {  
        Add(new PersonName("Willa", "Cather"));  
        Add(new PersonName("Isak", "Dinesen"));  
        Add(new PersonName("Victor", "Hugo"));  
        Add(new PersonName("Jules", "Verne"));  
    }  
  }  
  
  public class PersonName  
  {  
      private string firstName;  
      private string lastName;  
  
      public PersonName(string first, string last)  
      {  
          this.firstName = first;  
          this.lastName = last;  
      }  
  
      public string FirstName  
      {  
          get { return firstName; }  
          set { firstName = value; }  
      }  
  
      public string LastName  
      {  
          get { return lastName; }  
          set { lastName = value; }  
      }  
  }  
```  
  
```vb  
Public Class NameList  
    Inherits ObservableCollection(Of PersonName)  
  
    ' Methods  
    Public Sub New()  
        MyBase.Add(New PersonName("Willa", "Cather"))  
        MyBase.Add(New PersonName("Isak", "Dinesen"))  
        MyBase.Add(New PersonName("Victor", "Hugo"))  
        MyBase.Add(New PersonName("Jules", "Verne"))  
    End Sub  
  
End Class  
  
Public Class PersonName  
    ' Methods  
    Public Sub New(ByVal first As String, ByVal last As String)  
        Me._firstName = first  
        Me._lastName = last  
    End Sub  
  
    ' Properties  
    Public Property FirstName() As String  
        Get  
            Return Me._firstName  
        End Get  
        Set(ByVal value As String)  
            Me._firstName = value  
        End Set  
    End Property  
  
    Public Property LastName() As String  
        Get  
            Return Me._lastName  
        End Get  
        Set(ByVal value As String)  
            Me._lastName = value  
        End Set  
    End Property  
  
    ' Fields  
    Private _firstName As String  
    Private _lastName As String  
End Class  
```  
  
 Você pode tornar a coleção disponível para associação da mesma maneira que faria com outros objetos de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], conforme descrito em [Tornar dados disponíveis para associação em XAML](how-to-make-data-available-for-binding-in-xaml.md). Por exemplo, você pode instanciar a coleção em [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e especificar a coleção como um recurso, como mostrado aqui:  
  
```xaml  
<Window  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  xmlns:c="clr-namespace:SDKSample"  
  x:Class="SDKSample.Window1"  
  Width="400"  
  Height="280"  
  Title="MultiBinding Sample">  
  
  <Window.Resources>  
    <c:NameList x:Key="NameListData"/>  
  
...  
  
</Window.Resources>  
```  
  
 Em seguida, você pode associar à coleção:  
  
```xaml  
<ListBox Width="200"  
         ItemsSource="{Binding Source={StaticResource NameListData}}"  
         ItemTemplate="{StaticResource NameItemTemplate}"  
         IsSynchronizedWithCurrentItem="True"/>  
```  
  
 A definição de `NameItemTemplate` não é mostrada aqui.  
  
> [!NOTE]
>  Os objetos em sua coleção devem atender aos requisitos descritos na [Visão geral da origem da associação](binding-sources-overview.md). Em particular, se você estiver usando <xref:System.Windows.Data.BindingMode.OneWay> ou <xref:System.Windows.Data.BindingMode.TwoWay> (por exemplo, você deseja que seu [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] atualizar quando as propriedades da fonte são alteradas dinamicamente), você deve implementar um mecanismo de notificação de alteração de propriedade adequado, como o <xref:System.ComponentModel.INotifyPropertyChanged>interface.  
  
 Para obter mais informações, consulte a seção Associando a coleções na [Visão geral de associação de dados](data-binding-overview.md).  
  
## <a name="see-also"></a>Consulte também

- [Classificar dados em uma exibição](how-to-sort-data-in-a-view.md)
- [Filtrar dados em uma exibição](how-to-filter-data-in-a-view.md)
- [Classificar e agrupar dados usando uma exibição em XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Visão geral da vinculação de dados](data-binding-overview.md)
- [Tópicos de instruções](data-binding-how-to-topics.md)
