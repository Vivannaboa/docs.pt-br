---
title: Quando implantar contêineres do Windows para o serviço de contêiner do Azure (ou seja, Kubernetes)
description: Modernizar aplicativos .NET existentes com contêineres do Windows e de nuvem do Azure | Quando implantar contêineres do Windows para o serviço de contêiner do Azure (ou seja, Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 0b803b104f905fddac7939d7b070c206aabffeda
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011964"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Quando implantar contêineres do Windows para o serviço de contêiner do Azure (ou seja, Kubernetes)

O serviço de contêiner do Azure otimiza a configuração de tecnologias e ferramentas de código-fonte aberto populares especialmente para o Azure. Você obtém uma solução aberta que oferece portabilidade para seus contêineres e sua configuração de aplicativo. Você selecionar o tamanho, o número de hosts e as ferramentas do orchestrator. O serviço de contêiner do Azure lida com a infraestrutura para você.

Se você já estiver trabalhando com código-fonte aberto orquestradores como Kubernetes, Docker Swarm ou DC/SO, você não precisa alterar suas práticas de gerenciamento existente para mover cargas de trabalho de contêiner para a nuvem. Use as ferramentas de gerenciamento de aplicativo que você já conhece e conectar-se por meio de pontos de extremidade de API padrão para o orquestrador de sua escolha.

Todos esses orquestradores são ambientes de maduros se você estiver usando contêineres do Docker do Linux, mas só pode estar em estado de visualização para contêineres do Windows.

Por exemplo, no Kubernetes, suporte para contêineres é nativo (cidadão de primeira classe), portanto, usar contêineres do Windows no Kubernetes também é eficaz (em visualização no ACS a partir do início de 2018).

Observação importante: O evoluído e "mais PaaS" versão do ACS (serviço de contêiner do Azure) para o Kubernetes é AKS (serviço de Kubernetes do Azure), no entanto, contêineres do Windows ainda não há suporte para a partir do Q2 2018, mas terá suporte em breve.

>[!div class="step-by-step"]
>[Anterior](when-to-deploy-windows-containers-to-service-fabric.md)
>[Próximo](choosing-azure-compute-options-for-container-based-applications.md)