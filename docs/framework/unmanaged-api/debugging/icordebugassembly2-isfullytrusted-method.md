---
title: Método ICorDebugAssembly2::IsFullyTrusted
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd3b977a894f8cb1fc9a866f5a43265d917db513
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645559"
---
# <a name="icordebugassembly2isfullytrusted-method"></a>Método ICorDebugAssembly2::IsFullyTrusted
Obtém um valor que indica se o assembly foi concedido confiança total pelo sistema de segurança de tempo de execução.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `pbFullyTrusted`  
 [out] `true` se o assembly tiver sido concedido confiança total pelo sistema de segurança de tempo de execução; caso contrário, `false`.  
  
## <a name="remarks"></a>Comentários  
 Esse método retorna um HRESULT de CORDBG_E_NOTREADY se a política de segurança para o assembly ainda não foi resolvida, ou seja, se não houver código no assembly foi executada ainda.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
