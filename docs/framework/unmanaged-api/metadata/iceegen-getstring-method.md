---
title: Método ICeeGen::GetString
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 70d78942d4db2fea2cc1ccbcc5ddb20d743e9fdf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044909"
---
# <a name="iceegengetstring-method"></a>Método ICeeGen::GetString
Obtém a cadeia de caracteres armazenada no endereço virtual relativo especificado.  
  
 Esse método é obsoleto e não deve ser usado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `RVA`  
 [in] O endereço virtual relativo da cadeia de caracteres para retornar.  
  
 `lpString`  
 [out] Cadeia de caracteres retornada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor.h  
  
 **Biblioteca:** Usado como um recurso em mscoree. dll  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

- [Interface ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
