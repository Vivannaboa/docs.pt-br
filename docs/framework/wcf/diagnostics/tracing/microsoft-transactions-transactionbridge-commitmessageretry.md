---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: 3c398aa13a8cd2b87068216d3c07fb29e1a27c3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997952"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a>Microsoft.Transactions.TransactionBridge.CommitMessageRetry
Uma tentativa de mensagem de confirmação foi enviada a um participante sem resposta.  
  
## <a name="description"></a>Descrição  
 Rastreados se o Gerenciador de transações local necessário reenviar uma mensagem de confirmação a um participante subordinado porque não recebeu uma resposta em uma determinada quantidade de tempo.  
  
## <a name="troubleshooting"></a>Solução de problemas  
 Investigar os potencial rede ou problemas do produto que evitar que sejam entregues em tempo de resposta.  Se muitas dessas mensagens são vistas, isso pode indicar problemas de infraestrutura ou tempos de resposta anormalmente longo. Os dois problemas reduzirá drasticamente a taxa de transferência de transações no sistema.  
  
## <a name="see-also"></a>Consulte também

- [Rastreamento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Usando o rastreamento para solucionar problemas do seu aplicativo](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnósticos](../../../../../docs/framework/wcf/diagnostics/index.md)
