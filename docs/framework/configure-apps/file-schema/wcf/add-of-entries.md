---
title: <add> de <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 1324803d7c0f127cfee9eadebff2672955780eda
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673635"
---
# <a name="add-of-entries"></a>\<Adicionar > de \<entradas >
Representa uma entrada de roteamento que mapeia um filtro para um ponto de extremidade do cliente que foi definido anteriormente. As mensagens que correspondem a esse filtro serão enviadas para este destino.  
  
 \<system.serviceModel>  
\<routing>  
\<filterTables>  
\<filterTable>  
\<entries>  
\<add>  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|backupList|Uma cadeia de caracteres que especifica uma referência a uma lista de pontos de extremidade de backup.|  
|ponto de extremidade|Uma cadeia de caracteres que especifica uma referência a um ponto de extremidade do cliente que receberá as mensagens que correspondem ao filtro especificado pelo `filterName` atributo.|  
|filterName|Uma cadeia de caracteres que especifica uma referência a um elemento de filtro.|  
|priority|Um inteiro que especifica a prioridade desta entrada.<br /><br /> As entradas na tabela de roteamento serão avaliadas com base na prioridade, com 0 sendo a prioridade mais baixa. Todas as entradas para uma prioridade específica são avaliadas simultaneamente, se nenhuma correspondência de entrada for encontrada para a prioridade atual, o próximo nível de prioridade será avaliado.<br /><br /> Esse valor é opcional.|  
  
### <a name="child-elements"></a>Elementos filho  
 nenhuma.  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Uma seção de configuração que contém as entradas de mapeamento de roteamento.|  
  
## <a name="see-also"></a>Consulte também

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
