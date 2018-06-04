---
title: -publicsign (opções do compilador C#)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: ec25f9c1f2ef943db41bcfa20c8efd1d05866acd
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472819"
---
# <a name="-publicsign-c-compiler-options"></a><span data-ttu-id="3e0fb-102">-publicsign (opções do compilador C#)</span><span class="sxs-lookup"><span data-stu-id="3e0fb-102">-publicsign (C# Compiler Options)</span></span>

<span data-ttu-id="3e0fb-103">Essa opção faz com que o compilador aplique uma chave pública, mas, na verdade, não assina o assembly.</span><span class="sxs-lookup"><span data-stu-id="3e0fb-103">This option causes the compiler to apply a public key but does not actually sign the assembly.</span></span> <span data-ttu-id="3e0fb-104">A opção **-publicsign** também define um bit no assembly que informa o tempo de execução que o arquivo realmente já está assinado.</span><span class="sxs-lookup"><span data-stu-id="3e0fb-104">The **-publicsign** option also sets a bit in the assembly that tells the runtime that the file is actually signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e0fb-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3e0fb-105">Syntax</span></span>

```console
-publicsign
```

## <a name="arguments"></a><span data-ttu-id="3e0fb-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="3e0fb-106">Arguments</span></span>

<span data-ttu-id="3e0fb-107">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="3e0fb-107">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e0fb-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="3e0fb-108">Remarks</span></span>

<span data-ttu-id="3e0fb-109">A opção **-publicsign** requer o uso de [-keyfile](keyfile-compiler-option.md) ou [-keycontainer](keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="3e0fb-109">The **-publicsign** option requires the use of the [-keyfile](keyfile-compiler-option.md) or [-keycontainer](keycontainer-compiler-option.md).</span></span> <span data-ttu-id="3e0fb-110">As opções **keyfile** ou **keycontainer** especificam a chave pública.</span><span class="sxs-lookup"><span data-stu-id="3e0fb-110">The **keyfile** or **keycontainer** options specify the public key.</span></span>

<span data-ttu-id="3e0fb-111">As opções **-publicsign** e **-delaysign** são mutuamente exclusivas.</span><span class="sxs-lookup"><span data-stu-id="3e0fb-111">The **-publicsign** and **-delaysign** options are mutually exclusive.</span></span>

<span data-ttu-id="3e0fb-112">Às vezes chamada de "assinatura falsa" ou "assinatura de OSS", a assinatura pública inclui a chave pública em um assembly de saída e define o sinalizador "assinado", mas, na verdade, não assina o assembly com uma chave privada.</span><span class="sxs-lookup"><span data-stu-id="3e0fb-112">Sometimes called "fake sign" or "OSS sign", public signing includes the public key in an output assembly and sets the "signed" flag, but doesn't actually sign the assembly with a private key.</span></span> <span data-ttu-id="3e0fb-113">Isso é útil para projetos de software livre em que as pessoas desejam criar assemblies compatíveis com os assemblies "totalmente assinados" lançados, mas não têm acesso à chave privada usada para assinar os assemblies.</span><span class="sxs-lookup"><span data-stu-id="3e0fb-113">This is useful for open source projects where people want to build assemblies which are compatible with the released "fully signed" assemblies, but don't have access to the private key used to sign the assemblies.</span></span> <span data-ttu-id="3e0fb-114">Como quase nenhum consumidor precisa verificar realmente se o assembly está totalmente assinado, esses assemblies criados publicamente podem ser usados em quase todos os cenários nos quais o assembly totalmente assinado seria usado.</span><span class="sxs-lookup"><span data-stu-id="3e0fb-114">Since almost no consumers actually need to check if the assembly is fully signed, these publicly built assemblies are useable in almost every scenario where the fully signed one would be used.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="3e0fb-115">Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3e0fb-115">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="3e0fb-116">Abra a página **Propriedades** do projeto.</span><span class="sxs-lookup"><span data-stu-id="3e0fb-116">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="3e0fb-117">Modifique a propriedade **Apenas adiar a assinatura**.</span><span class="sxs-lookup"><span data-stu-id="3e0fb-117">Modify the **Delay sign only** property.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e0fb-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3e0fb-118">See Also</span></span>
 [<span data-ttu-id="3e0fb-119">Opção -delaysign do compilador C#</span><span class="sxs-lookup"><span data-stu-id="3e0fb-119">C# Compiler -delaysign option</span></span>](delaysign-compiler-option.md)  
 [<span data-ttu-id="3e0fb-120">Opção -keyfile do compilador C#</span><span class="sxs-lookup"><span data-stu-id="3e0fb-120">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)  
 [<span data-ttu-id="3e0fb-121">Opção -keycontainer do compilador C#</span><span class="sxs-lookup"><span data-stu-id="3e0fb-121">C# Compiler -keycontainer option</span></span>](keycontainer-compiler-option.md)  
 [<span data-ttu-id="3e0fb-122">Opções do compilador de C#</span><span class="sxs-lookup"><span data-stu-id="3e0fb-122">C# Compiler Options</span></span>](index.md)  
 [<span data-ttu-id="3e0fb-123">Gerenciando propriedades de solução e de projeto</span><span class="sxs-lookup"><span data-stu-id="3e0fb-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)