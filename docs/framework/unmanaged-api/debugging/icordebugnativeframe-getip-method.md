---
title: Método ICorDebugNativeFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f913b742f7ece2f136454f801ae780124aed87
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987959"
---
# <a name="icordebugnativeframegetip-method"></a>Método ICorDebugNativeFrame::GetIP
Obtém o código nativo de deslocamento local ao qual o ponteiro de instrução está definido atualmente.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `pnOffset`  
 [out] Um ponteiro para o local de deslocamento no código nativo.  
  
## <a name="remarks"></a>Comentários  
 Se o registro de ativação que é representado por esse "ICorDebugNativeFrame" estiver ativo, o deslocamento é o endereço da próxima instrução a ser executada. Se este registro de ativação não estiver ativo, o deslocamento é o endereço da próxima instrução a ser executado quando o quadro de pilha for reativado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também
