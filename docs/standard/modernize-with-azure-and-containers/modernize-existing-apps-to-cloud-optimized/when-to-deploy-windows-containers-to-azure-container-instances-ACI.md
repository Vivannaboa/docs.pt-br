---
title: Quando implantar contêineres do Windows para instâncias de contêiner do Azure (ACI)
description: Modernizar aplicativos .NET existentes com contêineres do Windows e de nuvem do Azure | Quando implantar contêineres do Windows para instâncias de contêiner do Azure (ACI)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 03ee7c8b65e1a92dcc7fd40b44e9ba081f571487
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011977"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Quando implantar contêineres do Windows para instâncias de contêiner do Azure (ACI)

Instâncias de contêiner do Azure proposta de valor principal é que você pode imediatamente implantar contêineres para ele e você não precisa manter esse ambiente, você não precisa atualizar/aplicar patch do sistema operacional subjacente ou a máquinas virtuais, tudo isso é transparente e você acabou de implantar contêineres em um ambiente pronto para uso.

As razões e os cenários nos quais você iria querer usar ACI são semelhantes às principais cenários quando você usa VMs do Azure com os contêineres, basicamente, os cenários principais para usar instâncias de contêiner do Azure são:

- **Cenários de desenvolvimento/teste**
- **Automação de tarefas**
- **Agentes de CI/CD**
- **Processamento de lote pequeno/escala**
- **Aplicativos web simples**

O cenário de aplicativos web simples é um cenário razoável para ACI, mas leve em consideração que, pois em ACI, você pode ter apenas uma instância única de contêiner por imagem de contêiner, você não terá a alta disponibilidade e só possui escalabilidade limitada.

No entanto, mesmo quando ACI é considerado infraestrutura porque ele fornece apenas instâncias de contêiner único, há um enorme benefício em comparação às VMs comuns do Azure com o Windows Server. Com o ACI, você implantar apenas os contêineres em um ambiente mantido automaticamente e você paga apenas por esses contêineres. Você não precisa manter/atualização/patch VMs, portanto, é uma plataforma melhor na maioria dos cenários em que talvez você esteja usando VMs com contêineres. Usar ACI é muito simples, basta você implanta um contêiner, não é necessário para criar um ambiente de VM que você implantar apenas os contêineres.

Os principais benefícios de instâncias de contêiner do Azure (ACI) são:

- Execute contêineres sem gerenciar servidores
- Aumente a agilidade com contêineres sob demanda
- Implantar contêineres para a nuvem com sem precedentes simplicidade e agilidade — com um único comando.
- Proteger aplicativos com isolamento de hipervisor

Em resumo, com o ACI, você pode desenvolver aplicativos rapidamente sem gerenciar máquinas virtuais ou precisar aprender novas ferramentas. Ele é simplesmente o aplicativo em um contêiner em execução na nuvem.

> [!div class="step-by-step"]
> [Anterior](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Próximo](when-to-deploy-windows-containers-to-service-fabric.md)
