---
title: Método IGCHost::GetStats
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14751b41809eeda5e6bd990fae368879d0f30492
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927239"
---
# <a name="igchostgetstats-method"></a>Método IGCHost::GetStats
Obtém as estatísticas para o estado atual do sistema de coleta de lixo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `pStats`  
 [no, out] Um ponteiro para um [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estrutura que contém as estatísticas para o estado atual do sistema de coleta de lixo.  
  
## <a name="remarks"></a>Comentários  
 As estatísticas podem ser usadas por um sistema inteligente de alocação para ajudar o sistema de coleta de lixo funcionar. Por exemplo, o sistema de alocação pode determinar, depois de revisar as estatísticas, o que ele precisa adicionar mais memória ou forçar uma coleta.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** GCHost.idl, GCHost.h  
  
 **Biblioteca:** Incluído como um recurso em mscoree. dll  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Interface IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
