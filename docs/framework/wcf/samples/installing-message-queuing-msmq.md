---
title: Instalando o Enfileiramento de Mensagens (MSMQ)
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 64736f8f0a34a53658dd2838738a3d36b3891d2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954941"
---
# <a name="installing-message-queuing-msmq"></a>Instalando o Enfileiramento de Mensagens (MSMQ)
Os procedimentos a seguir mostram como instalar o Enfileiramento de Mensagens 4.0 e o Enfileiramento de Mensagens 3.0.  
  
> [!NOTE]
>  O Enfileiramento de Mensagens 4.0 não está disponível no [!INCLUDE[wxp](../../../../includes/wxp-md.md)] nem no [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a>Para instalar o Enfileiramento de Mensagens 4.0 no Windows Server 2008 ou no Windows Server 2008 R2  
  
1. No Gerenciador do servidor, clique em **recursos**.  
  
2. No painel direito, sob **resumo de recursos**, clique em **adicionar recursos**.  
  
3. Na janela resultante, expanda **enfileiramento**.  
  
4. Expandir **serviços de enfileiramento de mensagens**.  
  
5. Clique em **integração de serviços de diretório** (para computadores que ingressaram em um domínio), em seguida, clique em **suporte HTTP**.  
  
6. Clique em **próxima**, em seguida, clique em **instalar**.  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a>Para instalar o Enfileiramento de Mensagens 4.0 no Windows 7 ou no Windows Vista  
  
1. Abra **Painel de Controle**.  
  
2. Clique em **programas** e, em **programas e recursos**, clique em **ativar e desativar recursos do Windows**.  
  
3. Expanda o Servidor Fila MSMQ, expanda o Server Core Fila MSMQ e marque as caixas de seleção dos seguintes recursos do Enfileiramento de Mensagens a serem instalados:  
  
    - Integração de MSMQ com os Serviços de Domínio Active Directory (para computadores ingressos em um Domínio).  
  
    - Suporte a HTTP do MSMQ.  
  
4. Clique em **OK**.  
  
5. Se você for solicitado a reiniciar o computador, clique em **Okey** para concluir a instalação.  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a>Para instalar o Enfileiramento de Mensagens 3.0 no Windows XP e no Windows Server 2003  
  
1. Abra **Painel de Controle**.  
  
2. Clique em **adicionar ou remover programas** e, em seguida, clique em **adicionar componentes do Windows**.  
  
3. Selecione enfileiramento de mensagens e clique em **detalhes**.  
  
    > [!NOTE]
    >  Se você estiver executando o [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], selecione Servidor de Aplicativos para acessar o Enfileiramento de Mensagens.  
  
4. Verifique se a opção Suporte a HTTP do MSMQ está selecionada na página de detalhes.  
  
5. Clique em **Okey** para sair da página de detalhes e, em seguida, clique em **próxima**. Conclua a instalação.  
  
6. Se você for solicitado a reiniciar o computador, clique em **Okey** para concluir a instalação.  
  
## <a name="see-also"></a>Consulte também

- [Instruções de configuração](../../../../docs/framework/wcf/samples/set-up-instructions.md)
