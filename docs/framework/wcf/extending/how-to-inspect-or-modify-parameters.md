---
title: 'Como: inspecionar ou modificar parâmetros'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
ms.openlocfilehash: 2e294b7970a58fad9385802470a514e5a9240495
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766851"
---
# <a name="how-to-inspect-or-modify-parameters"></a>Como: inspecionar ou modificar parâmetros
Você pode inspecionar ou modificar as mensagens de entrada ou saídas para uma única operação em um objeto de cliente do Windows Communication Foundation (WCF) ou um serviço WCF, Implementando o <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface e inseri-lo no tempo de execução do cliente ou serviço. Normalmente um comportamento de operação é usado para adicionar os inspetores de parâmetro para uma única operação; outros comportamentos podem ser usados para fornecer acesso fácil ao tempo de execução em um escopo maior. Para obter mais informações, consulte [estendendo clientes](../../../../docs/framework/wcf/extending/extending-clients.md) e [estendendo Dispatchers](../../../../docs/framework/wcf/extending/extending-dispatchers.md).  
  
### <a name="inspecting-or-modifying-parameters"></a>Inspecionar ou modificar parâmetros  
  
1. Implementar a interface <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>.  
  
2. Implementar uma <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> ou <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (dependendo do escopo necessário) para adicionar o Inspetor de parâmetro como o <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> ou <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> propriedades.  
  
3. Inserir seu comportamento antes de chamar <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> ou o <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> método o <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Para obter detalhes, consulte [Configurando e estendendo o tempo de execução com comportamentos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Exemplo  
 Os exemplos de código a seguir mostram, na ordem:  
  
- Uma implementação de Inspetor de parâmetro.  
  
- A implementação de comportamento que insere o Inspetor de parâmetro usando um <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>e um <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.  
  
- Um arquivo de configuração que carrega e executa o comportamento de ponto de extremidade em um aplicativo cliente para inserir o Inspetor de parâmetro no cliente.  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a>Consulte também

- [Configurando e estendendo o tempo de execução com comportamentos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
