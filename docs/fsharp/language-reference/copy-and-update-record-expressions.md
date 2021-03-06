---
title: Copiar e atualizar expressões de registro
description: Saiba como escrever um 'Copiar e atualizar registro expression' que copia um existente atualizações de registro, campos de especificado e retorna o registro atualizado.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 5f9b13ebf6c456aff73872b7522d7670c068dd88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766039"
---
# <a name="copy-and-update-record-expressions"></a>Copiar e atualizar expressões de registro

Um *copiar e atualizar registro expressão* é uma expressão que copia um registro existente, atualiza os campos especificados e retorna o registro atualizado.

## <a name="syntax"></a>Sintaxe

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a>Comentários

Os registros são imutáveis, por padrão, para que nenhuma atualização para um registro existente seja possível. Para criar um registro atualizado em todos os campos de um registro precisa ser especificado novamente. Para simplificar essa tarefa uma *copiar e atualizar registro expressão* pode ser usado. Essa expressão usa um registro existente, cria um novo do mesmo tipo usando campos especificados da expressão e o campo ausente especificados pela expressão.
Isso pode ser útil quando você tem que copiar um registro existente e, possivelmente, alterar alguns dos valores de campo.

Veja, por exemplo, um registro recém-criado.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Se você atualizar somente no campo desse registro, você pode usar o *copiar e atualizar registro expressão* semelhante ao seguinte:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Consulte também

- [Registros](records.md)
- [Referência da Linguagem F#](index.md)