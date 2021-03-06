---
title: Introdução ao Tutorial2
ms.date: 03/30/2017
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
ms.openlocfilehash: 540765c09dceef583798ceaf1abf9f191f444697
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773523"
---
# <a name="getting-started-tutorial"></a>Guia de introdução ao tutorial
Esta seção contém um conjunto de tópicos de instruções passo a passo que apresentam a programação de aplicativos do Windows Workflow Foundation (WF). Siga os procedimentos deste tópico para criar um aplicativo que é um jogo de adivinhação de números. O primeiro tópico no tutorial conduziu pelas etapas para criar as atividades personalizadas necessárias para o fluxo de trabalho. No segundo tópico, estas atividades são montadas junto com atividades internas de fluxo de trabalho em um fluxo de trabalho de fluxograma. No terceiro tópico, o aplicativo host é configurado para executar o fluxo de trabalho e, no tópico final, é apresentada a persistência. Cada etapa neste processo depende das etapas anteriores. Portanto, é recomendável que você as conclua na ordem.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Como: Criar uma atividade](how-to-create-an-activity.md)  
 Descreve como criar uma atividade personalizada que deriva de <xref:System.Activities.NativeActivity%601>, e como compor essa atividade junto com uma atividade interna em uma atividade composta usando o designer de atividade.  
  
 [Como: Criar um fluxo de trabalho](how-to-create-a-workflow.md)  
 Descreve como criar fluxos de trabalho de fluxograma, sequenciais e de máquina de estado usando atividades internas e atividades personalizadas do tutorial anterior.  
  
 [Como: Executar um fluxo de trabalho](how-to-run-a-workflow.md)  
 Descreve como chamar um fluxo de trabalho de um ambiente de host, transmitir dados para dentro e para fora de um fluxo de trabalho e como retomar indicadores.  
  
 [Como: Criar e executar uma longa em execução de fluxo de trabalho](how-to-create-and-run-a-long-running-workflow.md)  
 Descreve como adicionar persistência a um aplicativo de fluxo de trabalho.  
  
 [Como: Criar um personalizado de participante de acompanhamento](how-to-create-a-custom-tracking-participant.md)  
 Descreve como criar um participante de rastreamento personalizado e um perfil de controle.  
  
 [Como: Hospedar várias versões de uma fluxo de trabalho lado a lado](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 Descreve como usar `WorkflowIdentity` para hospedar várias versões de um fluxo de trabalho lado a lado.  
  
 [Como: Atualizar a definição de uma instância de fluxo de trabalho em execução](how-to-update-the-definition-of-a-running-workflow-instance.md)  
 Descreve como usar a atualização dinâmica para modificar instâncias de fluxo de trabalho em execução.  
  
## <a name="see-also"></a>Consulte também

- [Programação do Windows Workflow Foundation](programming.md)
