---
title: 'Serviço: Chamadas com falha por segundo'
ms.date: 03/30/2017
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
ms.openlocfilehash: 595b623d70bad82ea39ab3ef93fb5fd499268ff2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915701"
---
# <a name="service-calls-faulted-per-second"></a>Serviço: Chamadas com falha por segundo
Nome do contador: Chamadas com falha por segundo.  
  
## <a name="description"></a>Descrição  
 Número de chamadas que retornaram falhas para esse serviço em um segundo.  
  
 Esse contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cujo valor é calculado usando a fórmula a seguir.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Em aplicativos do Windows Communication Foundation (WCF), métodos de serviço se comunicam usando mensagens de falha SOAP de informações de erro de processamento. Falhas de SOAP são tipos de mensagem que são incluídos nos metadados para uma operação de serviço e, portanto, crie um contrato de falha que os clientes podem usar para tornar sua execução mais robusta ou interativo. Como falhas de SOAP são demonstradas para clientes no formato XML, eles são altamente interoperáveis.  
  
## <a name="see-also"></a>Consulte também

- [Especificando e lidando com falhas em contratos e serviços](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
