---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 10789f9a2940c239ae20c8fd1e9d48bca0e820ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963690"
---
# <a name="contract"></a>Contrato
Contrato  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a>Métodos  
 A classe de contrato não define quaisquer métodos.  
  
## <a name="properties"></a>Propriedades  
 A classe de contrato tem as seguintes propriedades:  
  
### <a name="appdomainid"></a>AppDomainId  
 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 A id appdomain do appdomain que hospeda o contrato.  
  
### <a name="behaviors"></a>Comportamentos  
 Tipo de dados: Matriz de comportamento  
  
 Tipo de acesso: Somente leitura  
  
 Os comportamentos associados a esse contrato.  
  
### <a name="name"></a>Nome  
 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O nome do contrato em WSDL.  
  
### <a name="namespace"></a>Namespace  
 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O namespace do `portType` elemento no WSDL.  
  
### <a name="operations"></a>Operações  
 Tipo de dados: Matriz de operação  
  
 Tipo de acesso: Somente leitura  
  
 As operações do contrato.  
  
### <a name="processid"></a>ProcessId  
 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 O processo de identificação do processo que hospeda o contrato.  
  
### <a name="ref"></a>ref  
 Tipo de dados: Contrato  
  
 Tipo de acesso: Somente leitura  
  
 O tipo de retorno de chamada quando o contrato é um contrato duplex.  
  
### <a name="sessionmode"></a>SessionMode  
 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 Indica se o contrato requer a associação associada a este contrato para usar sessões de canal.  
  
### <a name="type"></a>Tipo  
 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O tipo do contrato.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definido no root\ServiceModel|  
  
## <a name="see-also"></a>Consulte também

- <xref:System.ServiceModel.Description.ContractDescription>
