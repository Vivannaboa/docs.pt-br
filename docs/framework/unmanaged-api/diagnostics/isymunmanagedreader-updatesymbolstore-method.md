---
title: Método ISymUnmanagedReader::UpdateSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f62c954bf9d73ab564eba388e742794a330362d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986317"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>Método ISymUnmanagedReader::UpdateSymbolStore
Atualiza o repositório de símbolos existente com um repositório de símbolos delta. Esse método é usado em cenários de editar e continuar para atualizar o repositório de símbolos para corresponder os deltas para o original (arquivo portable Executable).  
  
> [!NOTE]
>  Você precisa especificar apenas um dos `filename` ou `pIStream` parâmetros, não ambos. Se `filename` for especificado, o repositório de símbolos será atualizado com os símbolos no arquivo. Se `pIStream` for especificado, o repositório será atualizado com os dados a partir de <xref:System.Runtime.InteropServices.ComTypes.IStream>.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Parâmetros  
 `filename`  
 [in] O nome do arquivo que contém o repositório de símbolos.  
  
 `pIStream`  
 [in] O fluxo de arquivos, usado como uma alternativa para o `filename` parâmetro.  
  
## <a name="return-value"></a>Valor de retorno  
 S_OK se o método for bem-sucedido; Caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Consulte também

- [Interface ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
