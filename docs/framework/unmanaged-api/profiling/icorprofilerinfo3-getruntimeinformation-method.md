---
title: Método ICorProfilerInfo3::GetRuntimeInformation
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a13e3e525c7f019e7dc49111b88ac374345830af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000591"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>Método ICorProfilerInfo3::GetRuntimeInformation
Fornece informações de versão sobre o common language runtime (CLR) que está sendo analisado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `pClrInstanceId`  
 [out] A ID do representante de uma instância CLR em execução em um processo. Isso é o mesmo que o `ClrInstanceID` relatórios de rastreamento de eventos para eventos de inicialização do Windows (ETW).  
  
 `pRuntimeType`  
 [out] O tipo de tempo de execução. Este parâmetro retorna `COR_PRF_DESKTOP_CLR` para obter a versão da área de trabalho do CLR, ou `COR_PRF_CORE_CLR` para a versão principal do CLR usado no Silverlight.  
  
 `pMajorVersion`  
 [out] O número de versão principal do CLR.  
  
 `pMinorVersion`  
 [out] O número de versão secundária do CLR.  
  
 `pBuildVersion`  
 [out] O número de versão de compilação do CLR.  
  
 `pQFEVersion`  
 [out] O número de versão do CLR que está associado uma atualização de software.  
  
 `cchVersionString`  
 [in] O comprimento, em caracteres, do buffer que `szVersionString` aponta.  
  
 `pcchVersionString`  
 [out] O comprimento, em caracteres, de `szVersionString`.  
  
 `szVersionString`  
 [out] A cadeia de caracteres de versão do CLR.  
  
## <a name="remarks"></a>Comentários  
 Você pode passar null para qualquer parâmetro. No entanto, `pcchVersionString` não pode ser nulo, a menos que `szVersionString` também será null.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Interface ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfaces de criação de perfil](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Criação de perfil](../../../../docs/framework/unmanaged-api/profiling/index.md)
