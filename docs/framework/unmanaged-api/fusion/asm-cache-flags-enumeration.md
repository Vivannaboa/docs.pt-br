---
title: Enumeração ASM_CACHE_FLAGS
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 619643eb50abc75fd10d59b38767013b2617c8cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915285"
---
# <a name="asmcacheflags-enumeration"></a>Enumeração ASM_CACHE_FLAGS
Indica a origem de um assembly que é representado por [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) no cache de assembly global.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|Descrição|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|Enumera o cache de assemblies pré-compilados usando Ngen.exe.|  
|`ASM_CACHE_GAC`|Enumera o cache de assembly global.|  
|`ASM_CACHE_DOWNLOAD`|Enumera os assemblies que foram baixadas sob demanda ou que foram copiados em sombra.|  
|`ASM_CACHE_ROOT`|Indica que o [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) função deve retornar o caminho para o cache de assembly global para o common language runtime (CLR) versão 2.0. Significativos apenas no contexto de uma chamada para [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
|`ASM_CACHE_ROOT_EX`|Indica que o [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) função deve retornar o caminho para o cache de assembly global para a versão 4 do CLR. Significativos apenas no contexto de uma chamada para [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** Fusion.h  
  
 **Biblioteca:** Incluído como um recurso em mscoree. dll  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Função GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)
- [Interface IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
- [Enumerações de fusão](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
