---
title: <security> de <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: f1e166bec2254ed6d2c306eaccfa13e9fba1d70d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670557"
---
# <a name="security-of-basichttpbinding"></a>\<segurança > de \<basicHttpBinding >
Define os recursos de segurança de [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).  
  
 \<system.ServiceModel>  
\<bindings>  
\<basicHttpBinding>  
\<binding>  
\<segurança >  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|modo|Opcional. Especifica o tipo de segurança que é usado. O padrão é `None`. Esse atributo é do tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>modo de atributo  
  
|Valor|Descrição|  
|-----------|-----------------|  
|Nenhum|-Mensagens não são protegidas durante a transferência.|  
|Transporte|Segurança é fornecida usando o transporte HTTPS. As mensagens SOAP são protegidas usando HTTPS. O serviço é autenticado para o cliente usando o certificado do serviço x. 509. O cliente é autenticado usando o ClientCredentialType fornecido. Consulte a [ \<transporte >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).|  
|Mensagem|A segurança é fornecida usando a segurança de mensagem SOAP. Por padrão, o corpo é criptografado e assinado. Para essa associação, o sistema exige que o certificado do servidor ser fornecida para o cliente fora da banda. Válido somente `ClientCredentialType` para essa associação é `Certificate`.|  
|TransportWithMessageCredential|Autenticação de integridade, confidencialidade e servidor são fornecidas pela segurança de transporte. A autenticação de cliente é fornecida por meio de segurança da mensagem SOAP. Esse modo é relevante quando o usuário está se autenticando usando o nome de usuário/senha e não há uma implantação existente de HTTP para transferência segura de mensagens.|  
|TransportCredentialOnly|Esse modo não fornece confidencialidade e integridade de mensagens. Ele fornece autenticação de cliente com base em http. Esse modo deve ser usado com cuidado. Ele deve ser usado em ambientes onde a segurança do transporte está sendo fornecida por outros meios (como IPSec) e somente a autenticação do cliente é fornecida pela infraestrutura do WCF.|  
  
### <a name="child-elements"></a>Elementos filho  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|Define as configurações de segurança de transporte para um serviço HTTP básico. Esse elemento corresponde a <xref:System.ServiceModel.HttpTransportSecurity>.|  
|[\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|Define as configurações de segurança de mensagem para um serviço HTTP básico. Esse elemento corresponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.|  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|associação|O elemento de associação do [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).|  
  
## <a name="remarks"></a>Comentários  
 Por padrão, a mensagem SOAP não é protegida e o cliente não está autenticado. Esse elemento permite que você defina as configurações de segurança adicional para o `basicHttpBinding` elemento.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [Protegendo serviços e clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Selecionando um tipo de credencial](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [Associações](../../../../../docs/framework/wcf/bindings.md)
- [Configurando associações fornecidas pelo sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Usando associações para configurar serviços e clientes](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
