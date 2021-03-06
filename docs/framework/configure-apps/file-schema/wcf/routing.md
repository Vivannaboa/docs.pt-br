---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: cc7c1a64f9481a7ab41cf35241ade04bd690dae0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786380"
---
# <a name="routing"></a>\<routing>

Representa uma seção de configuração para definir um conjunto de filtros de roteamento, que determinam o tipo do Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> a ser usada ao avaliar mensagens recebidas, bem como roteamento de tabelas que definem os pontos de extremidade de destino para envie mensagens para quando um filtro corresponde.

[**\<system.serviceModel>**](system-servicemodel.md)   
&nbsp;&nbsp;**\<routing>**
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String"
               filterName="String"
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos

As seções a seguir descrevem atributos, elementos filho e elementos pai.

### <a name="attributes"></a>Atributos

Nenhum

### <a name="child-elements"></a>Elementos filho

|     | Descrição |
| --- | ----------- |
| [**\<filters>**](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | Contém um conjunto de filtros de roteamento que determinam que o tipo de MessageFilter do Windows Communication Foundation (WCF) será usado ao avaliar mensagens recebidas. |
| [**\<filterTables>**](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | Contém mapeamentos entre os filtros de roteamento e os pontos de extremidade de destino para especificar qual ponto de extremidade usado quando o filtro corresponde. |

### <a name="parent-elements"></a>Elementos pai

|     | Descrição |
| --- | ----------- |
| **\<system.ServiceModel>** | O elemento raiz de todos os elementos de configuração do WCF. |

## <a name="see-also"></a>Consulte também

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
