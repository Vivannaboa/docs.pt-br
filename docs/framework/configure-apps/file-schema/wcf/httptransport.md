---
title: <httpTransport>
ms.date: 03/30/2017
ms.assetid: 8b30c065-b32a-4fa3-8eb4-5537a9c6b897
ms.openlocfilehash: 7a06772f078f9187298ad0b4b9c8b0f51c849928
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756059"
---
# <a name="httptransport"></a>\<httpTransport>
Especifica um transporte HTTP para transmissão de mensagens SOAP para uma associação personalizada.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<httpTransport>  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<httpTransport allowCookies="Boolean"
               authenticationScheme="Digest/Negotiate/Ntlm/Basic/Anonymous"
               bypassProxyOnLocal="Boolean"
               hostnameComparisonMode="StrongWildcard/Exact/WeakWildcard"
               keepAliveEnabled="Boolean"
               maxBufferSize="Integer"
               proxyAddress="Uri"
               proxyAuthenticationScheme="None/Digest/Negotiate/Ntlm/Basic/Anonymous"
               realm="String"
               transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"
               unsafeConnectionNtlmAuthentication="Boolean"
               useDefaultWebProxy="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|allowCookies|Um valor booliano que especifica se o cliente aceita cookies e propaga-os em solicitações futuras. O padrão é `false`.<br /><br /> Você pode usar esse atributo quando você interage com os serviços Web ASMX que usam cookies. Dessa forma, você pode ter certeza de que os cookies retornados do servidor são copiados automaticamente para todas as solicitações futuras de cliente para o serviço.|  
|authenticationScheme|Especifica o protocolo usado para autenticar solicitações de cliente sendo processadas por um ouvinte HTTP. Os valores válidos incluem o seguinte:<br /><br /> -Resumo: Especifica a autenticação Digest.<br />-Negotiate: Negocia com o cliente para determinar o esquema de autenticação. Se o cliente e o servidor oferecem suporte ao Kerberos, ele é usado; caso contrário, o NTLM é usado.<br />-   Ntlm: Especifica autenticação NTLM.<br />-Básico: Especifica autenticação básica.<br />-Anônimo: Especifica autenticação anônima.<br /><br /> O padrão é anônimo. Esse atributo é do tipo <xref:System.Net.AuthenticationSchemes>. Esse atributo só pode ser definido uma vez.|  
|bypassProxyOnLocal|Um valor booliano que indica se deve ignorar o servidor proxy para endereços locais. O padrão é `false`.<br /><br /> Um endereço local é aquele que está na rede local ou da intranet.<br /><br /> Windows Communication Foundation (WCF) sempre ignora o proxy se o endereço do serviço começa com `http://localhost`.<br /><br /> Se você deseja que os clientes para passar por um proxy ao conversar com os serviços no mesmo computador, você deve usar o nome de host em vez do localhost.|  
|hostnameComparisonMode|Especifica o modo de comparação de nome de host HTTP usado para analisar URIs. Os valores válidos são,<br /><br /> -StrongWildcard: ("+") corresponde a todos os possíveis nomes de host no contexto do esquema especificado, porta e o URI relativo.<br />-Exato: sem curingas<br />-WeakWildcard: ("\*") corresponde ao nome de host de todos os possíveis no contexto do esquema especificado, porta e UIR relativa que não foram correspondidas explicitamente ou por meio do mecanismo de curinga forte.<br /><br /> Esse atributo é do tipo <xref:System.ServiceModel.HostNameComparisonMode>. O padrão é <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>.|  
|keepAliveEnabled|Um valor booliano que especifica se é necessário fazer uma conexão persistente para o recurso de internet.|  
|maxBufferSize|Um inteiro positivo que especifica o tamanho máximo do buffer. O padrão é 524288|  
|proxyAddress|Um URI que especifica o endereço do proxy HTTP. Se `useSystemWebProxy` está `true`, essa configuração deve ser `null`. O padrão é `null`.|  
|proxyAuthenticationScheme|Especifica o protocolo usado para autenticar solicitações de cliente sendo processadas por um proxy HTTP. Os valores válidos incluem o seguinte:<br /><br /> -None: Nenhuma autenticação é executada.<br />-Resumo: Especifica a autenticação Digest.<br />-Negotiate: Negocia com o cliente para determinar o esquema de autenticação. Se o cliente e o servidor oferecem suporte ao Kerberos, ele é usado; caso contrário, o NTLM é usado.<br />-   Ntlm: Especifica autenticação NTLM.<br />-Básico: Especifica autenticação básica.<br />-Anônimo: Especifica autenticação anônima.<br /><br /> O padrão é anônimo. Esse atributo é do tipo <xref:System.Net.AuthenticationSchemes>. Observe que <xref:System.Net.AuthenticationSchemes.IntegratedWindowsAuthentication?displayProperty=nameWithType> não tem suporte.|  
|território|Uma cadeia de caracteres que especifica o domínio a ser usado no proxy/servidor. O padrão é uma cadeia de caracteres vazia.<br /><br /> Servidores usam realms para dividir os recursos protegidos. Cada partição pode ter seu próprio banco de dados de esquema e/ou autorização de autenticação. Realms são usados somente para basic e autenticação digest. Depois que um cliente é autenticado com êxito, a autenticação é válida para todos os recursos de um determinado território. Para obter uma descrição detalhada de territórios, consulte RFC 2617 na [site do IETF](https://www.ietf.org).|  
|transferMode|Especifica se as mensagens são armazenadas em buffer ou transmitidas ou uma solicitação ou resposta. Os valores válidos incluem o seguinte:<br /><br /> -Armazenada em buffer: As mensagens de solicitação e resposta são armazenados em buffer.<br />-Transmitidos: As mensagens de solicitação e resposta são transmitidas.<br />-   StreamedRequest: A mensagem de solicitação é transmitida e a mensagem de resposta é armazenada em buffer.<br />-   StreamedResponse: A mensagem de solicitação é armazenada em buffer e a mensagem de resposta é transmitida.<br /><br /> O padrão é armazenada em buffer. Esse atributo é do tipo <xref:System.ServiceModel.TransferMode> .|  
|unsafeConnectionNtlmAuthentication|Um valor booliano que especifica se o compartilhamento de Conexão não segura está habilitada no servidor. O padrão é `false`. Se estiver habilitado, a autenticação NTLM será executada uma vez em cada conexão TCP.|  
|useDefaultWebProxy|Um valor booliano que especifica se as configurações de proxy de todo o computador são usadas em vez de configurações específicas do usuário. O padrão é `true`.|  
  
### <a name="child-elements"></a>Elementos filho  
 Nenhum  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Define todos os recursos de associação de associação personalizada.|  
  
## <a name="remarks"></a>Comentários  
 O `httpTransport` elemento é o ponto de partida para criar uma associação personalizada que implementa o protocolo de transporte HTTP. O HTTP é o transporte usado para fins de interoperabilidade primário. Esse transporte é suportado pelo Windows Communication Foundation (WCF) para garantir a interoperabilidade com outras pilhas de serviços não WCF Web.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.ServiceModel.Configuration.HttpTransportElement>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Transportes](../../../../../docs/framework/wcf/feature-details/transports.md)
- [Escolhendo um transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [Associações](../../../../../docs/framework/wcf/bindings.md)
- [Estendendo associações](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Associações personalizadas](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
