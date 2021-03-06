---
title: Método ICLRRuntimeInfo::GetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c39ad4638c7db45c481bd3dfccb0a82759397aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771742"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>Método ICLRRuntimeInfo::GetDefaultStartupFlags
Obtém os sinalizadores de inicialização e o arquivo de configuração de host que será usado para iniciar o tempo de execução.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `pdwStartupFlags`  
 [out] Um ponteiro para os sinalizadores de inicialização de host que estão atualmente definidas.  
  
 `pwzHostConfigFile`  
 [out] Um ponteiro para o caminho do diretório do arquivo de configuração de host atual.  
  
 `pcchHostConfigFile`  
 [no, out] O tamanho de entrada na `pwzHostConfigFile`, para evitar estouros de buffer. Se `pwzHostConfigFile` é nulo, o método retorna o tamanho necessário do `pwzHostConfigFile` para pré-alocação.  
  
## <a name="return-value"></a>Valor de retorno  
 Esse método retorna o HRESULT específico a seguir, bem como erros HRESULT que indicam falha do método.  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|O método foi concluído com êxito.|  
  
## <a name="remarks"></a>Comentários  
 Esse método retorna os valores de sinalizador padrão (`STARTUP_CONCURRENT_GC` e `NULL`), ou os valores fornecidos por uma chamada anterior para o [método iclrruntimeinfo:: Setdefaultstartupflags](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), ou os valores definidos por qualquer um do `CorBind*` métodos de se eles estiverem associados a esse tempo de execução.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** MetaHost.h  
  
 **Biblioteca:** Incluído como um recurso em mscoree. dll  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Interface ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Hospedagem de Interfaces](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedagem](../../../../docs/framework/unmanaged-api/hosting/index.md)
