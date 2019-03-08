---
title: Tipos de referência anuláveis
description: Este artigo fornece uma visão geral dos tipos de referência que permitem valor nulo, adicionados no C# 8. Você aprenderá como o recurso fornece segurança com relação a exceções de referência nula para projetos novos e existentes.
ms.date: 02/19/2019
ms.openlocfilehash: 1eb4ccb5ec4397cb81aab37c13a31c41533238e9
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57411541"
---
# <a name="nullable-reference-types"></a><span data-ttu-id="b1931-104">Tipos de referência anuláveis</span><span class="sxs-lookup"><span data-stu-id="b1931-104">Nullable reference types</span></span>

<span data-ttu-id="b1931-105">O C# 8.0 apresenta **tipos de referência que permitem valor nulo** e **tipos de referência que não permitem valor nulo** que permitem que você crie importantes instruções sobre as propriedades para variáveis de tipo de referência:</span><span class="sxs-lookup"><span data-stu-id="b1931-105">C# 8.0 introduces **nullable reference types** and **non-nullable reference types** that enable you to make important statements about the properties for reference type variables:</span></span>

- <span data-ttu-id="b1931-106">**Uma referência não deve ser nula**.</span><span class="sxs-lookup"><span data-stu-id="b1931-106">**A reference is not supposed to be null**.</span></span> <span data-ttu-id="b1931-107">Quando as variáveis não devem ser nulas, o compilador impõe regras que garantem que seja seguro desreferenciar essas variáveis sem verificar primeiro que ela não está nula:</span><span class="sxs-lookup"><span data-stu-id="b1931-107">When variables aren't supposed to be null, the compiler enforces rules that ensure it is safe to dereference these variables without first checking that it isn't null:</span></span>
  - <span data-ttu-id="b1931-108">A variável deve ser inicializada para um valor não nulo.</span><span class="sxs-lookup"><span data-stu-id="b1931-108">The variable must be initialized to a non-null value.</span></span>
  - <span data-ttu-id="b1931-109">A variável nunca pode receber o valor `null`.</span><span class="sxs-lookup"><span data-stu-id="b1931-109">The variable can never be assigned the value `null`.</span></span>
- <span data-ttu-id="b1931-110">**Uma referência pode ser nula**.</span><span class="sxs-lookup"><span data-stu-id="b1931-110">**A reference may be null**.</span></span> <span data-ttu-id="b1931-111">Quando variáveis puderem ser nulas, o compilador imporá diferentes regras para garantir que você verificou corretamente se há uma referência nula:</span><span class="sxs-lookup"><span data-stu-id="b1931-111">When variables may be null, the compiler enforces different rules to ensure that you've correctly checked for a null reference:</span></span>
  - <span data-ttu-id="b1931-112">a variável só poderá ser desreferenciada quando o compilador puder garantir que o valor não é nulo.</span><span class="sxs-lookup"><span data-stu-id="b1931-112">The variable may only be dereferenced when the compiler can guarantee that the value isn't null.</span></span>
  - <span data-ttu-id="b1931-113">Essas variáveis podem ser inicializadas com o valor `null` padrão e receber o valor `null` em outro código.</span><span class="sxs-lookup"><span data-stu-id="b1931-113">These variables may be initialized with the default `null` value and may be assigned the value `null` in other code.</span></span>

<span data-ttu-id="b1931-114">Esse novo recurso oferece benefícios significativos com relação à manipulação de variáveis de referência em versões anteriores do C#, em que a intenção do design não poderia ser determinada na declaração da variável.</span><span class="sxs-lookup"><span data-stu-id="b1931-114">This new feature provides significant benefits over the handling of reference variables in earlier versions of C# where the design intent couldn't be determined from the variable declaration.</span></span> <span data-ttu-id="b1931-115">O compilador não forneceu segurança com relação a exceções de referência nula para tipos de referência:</span><span class="sxs-lookup"><span data-stu-id="b1931-115">The compiler didn't provide safety against null reference exceptions for reference types:</span></span>

- <span data-ttu-id="b1931-116">**Uma referência pode ser nula**.</span><span class="sxs-lookup"><span data-stu-id="b1931-116">**A reference can be null**.</span></span> <span data-ttu-id="b1931-117">Nenhum aviso é emitido quando um tipo de referência é inicializado para nulo ou atribuído posteriormente a nulo.</span><span class="sxs-lookup"><span data-stu-id="b1931-117">No warnings are issued when a reference type is initialized to null, or later assigned to null.</span></span>
- <span data-ttu-id="b1931-118">**Uma referência é considerada não nula**.</span><span class="sxs-lookup"><span data-stu-id="b1931-118">**A reference is assumed to be not null**.</span></span> <span data-ttu-id="b1931-119">O compilador não emite nenhum aviso quando os tipos de referência são desreferenciados.</span><span class="sxs-lookup"><span data-stu-id="b1931-119">The compiler doesn't issue any warnings when reference types are dereferenced.</span></span> <span data-ttu-id="b1931-120">(Com referências que permitem valor nulo, o compilador emite avisos sempre que você desreferencia uma variável que pode ser nula).</span><span class="sxs-lookup"><span data-stu-id="b1931-120">(With nullable references,  the compiler issues warnings whenever you dereference a variable that may be null).</span></span>

<span data-ttu-id="b1931-121">Com a adição de tipos de referência que permitem valor nulo, é possível declarar sua intenção mais claramente.</span><span class="sxs-lookup"><span data-stu-id="b1931-121">With the addition of nullable reference types, you can declare your intent more clearly.</span></span> <span data-ttu-id="b1931-122">O valor `null` é a maneira correta de representar que uma variável não se refere a um valor.</span><span class="sxs-lookup"><span data-stu-id="b1931-122">The `null` value is the correct way to represent that a variable doesn't refer to a value.</span></span> <span data-ttu-id="b1931-123">Não use esse recurso para remover todos os valores `null` do seu código.</span><span class="sxs-lookup"><span data-stu-id="b1931-123">Don't use this feature to remove all `null` values from your code.</span></span> <span data-ttu-id="b1931-124">Em vez disso, você deve declarar sua intenção par ao compilador e para outros desenvolvedores que leem seu código.</span><span class="sxs-lookup"><span data-stu-id="b1931-124">Rather, you should declare your intent to the compiler and other developers that read your code.</span></span> <span data-ttu-id="b1931-125">Ao declarar sua intenção, o compilador informa quando você escreve um código inconsistente com essa intenção.</span><span class="sxs-lookup"><span data-stu-id="b1931-125">By declaring your intent, the compiler informs you when you write code that is inconsistent with that intent.</span></span>

<span data-ttu-id="b1931-126">Um **tipo de referência que permite valor nulo** é indicado usando a mesma sintaxe que [tipos de valor que permitem valor nulo](programming-guide/nullable-types/index.md): um `?` é acrescentado ao tipo da variável.</span><span class="sxs-lookup"><span data-stu-id="b1931-126">A **nullable reference type** is noted using the same syntax as [nullable value types](programming-guide/nullable-types/index.md): a `?` is appended to the type of the variable.</span></span> <span data-ttu-id="b1931-127">Por exemplo, a seguinte declaração de variável representa uma variável de cadeia de caracteres que permite valor nulo, `name`:</span><span class="sxs-lookup"><span data-stu-id="b1931-127">For example, the following variable declaration represents a nullable string variable, `name`:</span></span>

```csharp
string? name;
```

<span data-ttu-id="b1931-128">Qualquer variável em que o `?` não é acrescentado ao nome do tipo é um **tipo de referência que não permite valor nulo**.</span><span class="sxs-lookup"><span data-stu-id="b1931-128">Any variable where the `?` is not appended to the type name is a **non-nullable reference type**.</span></span> <span data-ttu-id="b1931-129">Isso inclui todas as variáveis de tipo de referência no código existente quando você habilitou esse recurso.</span><span class="sxs-lookup"><span data-stu-id="b1931-129">That includes all reference type variables in existing code when you have enabled this feature.</span></span>

<span data-ttu-id="b1931-130">O compilador usa uma análise estática para determinar se uma referência que permite valor nulo é conhecida como não nula.</span><span class="sxs-lookup"><span data-stu-id="b1931-130">The compiler uses static analysis to determine if a nullable reference is known to be non-null.</span></span> <span data-ttu-id="b1931-131">O compilador informa se você desreferencia uma referência quer permite valor nulo quando ela pode ser nula.</span><span class="sxs-lookup"><span data-stu-id="b1931-131">The compiler warns you if you dereference a nullable reference when it may be null.</span></span> <span data-ttu-id="b1931-132">É possível substituir esse comportamento usando o **operador tolerante a nulo** (`!`) seguindo um nome de variável.</span><span class="sxs-lookup"><span data-stu-id="b1931-132">You can override this behavior by using the **null-forgiving operator** (`!`) following a variable name.</span></span> <span data-ttu-id="b1931-133">Por exemplo, se você sabe que a variável `name` não é nula, mas o compilador emite um aviso, é possível escrever o seguinte código para substituir a análise do compilador:</span><span class="sxs-lookup"><span data-stu-id="b1931-133">For example, if you know the `name` variable isn't null but the compiler issues a warning, you can write the following code to override the compiler's analysis:</span></span>

```csharp
name!.Length;
```

<span data-ttu-id="b1931-134">é possível ler detalhes sobre esse operador na proposta de especificação de [tipos de referência que permitem valor nulo do rascunho](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) no GitHub.</span><span class="sxs-lookup"><span data-stu-id="b1931-134">You can read details about this operator in the [draft nullable reference types](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) specification proposal on GitHub.</span></span>

## <a name="nullability-of-types"></a><span data-ttu-id="b1931-135">Possibilidade de nulidade de tipos</span><span class="sxs-lookup"><span data-stu-id="b1931-135">Nullability of types</span></span>

<span data-ttu-id="b1931-136">Qualquer tipo de referência pode ter uma das quatro *nulidades*, que descreve quando os avisos são gerados:</span><span class="sxs-lookup"><span data-stu-id="b1931-136">Any reference type can have one of four *nullabilities*, which describes when warnings are generated:</span></span>

- <span data-ttu-id="b1931-137">*Não anulável*: Null não pode ser atribuído a variáveis desse tipo.</span><span class="sxs-lookup"><span data-stu-id="b1931-137">*Nonnullable*: Null can't be assigned to variables of this type.</span></span> <span data-ttu-id="b1931-138">As variáveis desse tipo não precisam ser verificadas quanto à nulidade antes de desreferenciar.</span><span class="sxs-lookup"><span data-stu-id="b1931-138">Variables of this type don't need to be null-checked before dereferencing.</span></span>
- <span data-ttu-id="b1931-139">*Anulável*: Null pode ser atribuído a variáveis desse tipo.</span><span class="sxs-lookup"><span data-stu-id="b1931-139">*Nullable*: Null can be assigned to variables of this type.</span></span> <span data-ttu-id="b1931-140">Desreferenciar variáveis desse tipo sem verificar primeiro se há `null` gera um aviso.</span><span class="sxs-lookup"><span data-stu-id="b1931-140">Dereferencing variables of this type without first checking for `null` causes a warning.</span></span>
- <span data-ttu-id="b1931-141">*Alheia*: Esse é o estado pré-C# 8.</span><span class="sxs-lookup"><span data-stu-id="b1931-141">*Oblivious*: This is the pre-C# 8 state.</span></span> <span data-ttu-id="b1931-142">As variáveis desse tipo podem ser desreferenciadas ou atribuídas sem avisos.</span><span class="sxs-lookup"><span data-stu-id="b1931-142">Variables of this type can be dereferenced or assigned without warnings.</span></span>
- <span data-ttu-id="b1931-143">*Desconhecido*: Esse é geralmente para parâmetros de tipo em que restrições não informam o compilador de que o tipo deve ser *anulável* ou *não anulável*.</span><span class="sxs-lookup"><span data-stu-id="b1931-143">*Unknown*: This is generally for type parameters where constraints don't tell the compiler that the type must be *nullable* or *nonnullable*.</span></span>

<span data-ttu-id="b1931-144">A nulidade de um tipo em uma declaração de variável é controlada pelo *contexto que permite valor nulo* no qual a variável é declarada.</span><span class="sxs-lookup"><span data-stu-id="b1931-144">The nullability of a type in a variable declaration is controlled by the *nullable context* in which the variable is declared.</span></span>

## <a name="nullable-contexts"></a><span data-ttu-id="b1931-145">Contextos que permitem valor nulo</span><span class="sxs-lookup"><span data-stu-id="b1931-145">Nullable contexts</span></span>

<span data-ttu-id="b1931-146">Contextos que permitem valor nulo habilitam o controle refinado para a maneira como o compilador interpreta variáveis de tipo de referência.</span><span class="sxs-lookup"><span data-stu-id="b1931-146">Nullable contexts enable fine-grained control for how the compiler interprets reference type variables.</span></span> <span data-ttu-id="b1931-147">O **contexto de anotação que permite valor nulo** de qualquer linha de origem determinada é `enabled` ou `disabled`.</span><span class="sxs-lookup"><span data-stu-id="b1931-147">The **nullable annotation context** of any given source line is `enabled` or `disabled`.</span></span> <span data-ttu-id="b1931-148">Você pode pensar no compilador pré-C# 8 como compilando todo seu código em um contexto que permite valor nulo `disabled`: Qualquer tipo de referência pode ser nulo.</span><span class="sxs-lookup"><span data-stu-id="b1931-148">You can think of the pre-C# 8 compiler as compiling all your code in a `disabled` nullable context: Any reference type may be null.</span></span> <span data-ttu-id="b1931-149">O **contexto de avisos que permite valor nulo** pode ser definido como `enabled`, `disabled` ou `safeonly`.</span><span class="sxs-lookup"><span data-stu-id="b1931-149">The **nullable warnings context** may be set to `enabled`, `disabled`, or `safeonly`.</span></span> <span data-ttu-id="b1931-150">O contexto de avisos que permite valor nulo especifica os avisos gerados pelo compilador usando sua análise de fluxo.</span><span class="sxs-lookup"><span data-stu-id="b1931-150">The nullable warnings context specifies the warnings generated by the compiler using its flow analysis.</span></span>

<span data-ttu-id="b1931-151">O contexto de anotação que permite valor nulo e o contexto de aviso que permite valor nulo podem ser definidos para um projeto que usa o elemento `NullableContextOptions` no seu arquivo `csproj`.</span><span class="sxs-lookup"><span data-stu-id="b1931-151">The nullable annotation context and nullable warning context can be set for a project using the `NullableContextOptions` element in your `csproj` file.</span></span> <span data-ttu-id="b1931-152">Esse elemento configura como o compilador interpreta a nulidade de tipos e quais avisos são gerados.</span><span class="sxs-lookup"><span data-stu-id="b1931-152">This element configures how the compiler interprets the nullability of types and what warnings are generated.</span></span> <span data-ttu-id="b1931-153">As configurações válidas são:</span><span class="sxs-lookup"><span data-stu-id="b1931-153">Valid settings are:</span></span>

- <span data-ttu-id="b1931-154">`enable`: O contexto de anotação que permite valor nulo está **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-154">`enable`: The nullable annotation context is **enabled**.</span></span> <span data-ttu-id="b1931-155">O contexto de aviso que permite valor nulo está **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-155">The nullable warning context is **enabled**.</span></span>
  - <span data-ttu-id="b1931-156">Variáveis de um tipo de referência, `string` por exemplo, não permitem valor nulo.</span><span class="sxs-lookup"><span data-stu-id="b1931-156">Variables of a reference type, `string` for example, are non-nullable.</span></span>  <span data-ttu-id="b1931-157">Todos os avisos de nulidade estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="b1931-157">All nullability warnings are enabled.</span></span>
- <span data-ttu-id="b1931-158">`disable`: O contexto de anotação que permite valor nulo está **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-158">`disable`: The nullable annotation context is **disabled**.</span></span> <span data-ttu-id="b1931-159">O contexto de aviso que permite valor nulo está **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-159">The nullable warning context is **disabled**.</span></span>
  - <span data-ttu-id="b1931-160">As variáveis de um tipo de referência são alheias, como as versões anteriores do C#.</span><span class="sxs-lookup"><span data-stu-id="b1931-160">Variables of a reference type are oblivious, just like earlier versions of C#.</span></span> <span data-ttu-id="b1931-161">Todos os avisos de nulidade estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="b1931-161">All nullability warnings are disabled.</span></span>
- <span data-ttu-id="b1931-162">`safeonly`: O contexto de anotação que permite valor nulo está **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-162">`safeonly`: The nullable annotation context is **enabled**.</span></span> <span data-ttu-id="b1931-163">O contexto de aviso que permite valor nulo é **safeonly**.</span><span class="sxs-lookup"><span data-stu-id="b1931-163">The nullable warning context is **safeonly**.</span></span>
  - <span data-ttu-id="b1931-164">As variáveis de um tipo de referência são não anuláveis.</span><span class="sxs-lookup"><span data-stu-id="b1931-164">Variables of a reference type are nonnullable.</span></span> <span data-ttu-id="b1931-165">Todos os avisos de nulidade de segurança estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="b1931-165">All safety nullability warnings are enabled.</span></span>
- <span data-ttu-id="b1931-166">`warnings`: O contexto de anotação que permite valor nulo está **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-166">`warnings`: The nullable annotation context is **disabled**.</span></span> <span data-ttu-id="b1931-167">O contexto de aviso que permite valor nulo está **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-167">The nullable warning context is **enabled**.</span></span>
  - <span data-ttu-id="b1931-168">As variáveis de um tipo de referência são óbvias.</span><span class="sxs-lookup"><span data-stu-id="b1931-168">Variables of a reference type are oblivious.</span></span> <span data-ttu-id="b1931-169">Todos os avisos de nulidade estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="b1931-169">All nullability warnings are enabled.</span></span>
- <span data-ttu-id="b1931-170">`safeonlywarnings`: O contexto de anotação que permite valor nulo está **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-170">`safeonlywarnings`: The nullable annotation context is **disabled**.</span></span> <span data-ttu-id="b1931-171">O contexto de aviso que permite valor nulo é **safeonly**.</span><span class="sxs-lookup"><span data-stu-id="b1931-171">The nullable warning context is **safeonly**.</span></span>
  - <span data-ttu-id="b1931-172">As variáveis de um tipo de referência são óbvias.</span><span class="sxs-lookup"><span data-stu-id="b1931-172">Variables of a reference type are oblivious.</span></span> <span data-ttu-id="b1931-173">Todos os avisos de nulidade de segurança estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="b1931-173">All safety nullability warnings are enabled.</span></span>

<span data-ttu-id="b1931-174">Também é possível usar diretivas para definir esses mesmos contextos em qualquer lugar no seu projeto:</span><span class="sxs-lookup"><span data-stu-id="b1931-174">You can also use directives to set these same contexts anywhere in your project:</span></span>

- <span data-ttu-id="b1931-175">`#nullable enable`: define o contexto de anotação que permite valor nulo e o contexto de aviso que permite valor nulo como **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-175">`#nullable enable`: Sets the nullable annotation context and nullable warning context to **enabled**.</span></span>
- <span data-ttu-id="b1931-176">`#nullable disable`: define o contexto de anotação que permite valor nulo e o contexto de aviso que permite valor nulo como **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-176">`#nullable disable`: Sets the nullable annotation context and nullable warning context to **disabled**.</span></span>
- <span data-ttu-id="b1931-177">`#nullable safeonly`: define o contexto de anotação que permite valor nulo como **habilitado** e o contexto de aviso que permite valor nulo como **safeonly**.</span><span class="sxs-lookup"><span data-stu-id="b1931-177">`#nullable safeonly`: Set the nullable annotation context to **enabled**, and the warning context to **safeonly**.</span></span>
- <span data-ttu-id="b1931-178">`#nullable restore`: restaura o contexto de anotação que permite valor nulo e o contexto de aviso que permite valor nulo para as configurações do projeto.</span><span class="sxs-lookup"><span data-stu-id="b1931-178">`#nullable restore`: Restores the nullable annotation context and nullable warning context to the project settings.</span></span>
- <span data-ttu-id="b1931-179">`#pragma warning disable nullable`: definir o contexto de aviso que permite valor nulo como **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-179">`#pragma warning disable nullable`: Set the nullable warning context to **disabled**.</span></span>
- <span data-ttu-id="b1931-180">`#pragma warning enable nullable`: definir o contexto de aviso que permite valor nulo como **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-180">`#pragma warning enable nullable`: Set the nullable warning context to **enabled**.</span></span>
- <span data-ttu-id="b1931-181">`#pragma warning restore nullable`: restaura o contexto de aviso que permite valor nulo para as configurações do projeto.</span><span class="sxs-lookup"><span data-stu-id="b1931-181">`#pragma warning restore nullable`: Restores the nullable warning context to the project settings.</span></span>
- <span data-ttu-id="b1931-182">`#pragma warning safeonly nullable`: define o contexto de aviso que permite valor nulo como **safeonly**.</span><span class="sxs-lookup"><span data-stu-id="b1931-182">`#pragma warning safeonly nullable`: Sets the nullable warning context to **safeonly**.</span></span>

<span data-ttu-id="b1931-183">Os contextos padrão de aviso e de anotação que permitem valor nulo são `disabled`.</span><span class="sxs-lookup"><span data-stu-id="b1931-183">The default nullable annotation and warning contexts are `disabled`.</span></span> <span data-ttu-id="b1931-184">Essa decisão significa que seu código existente compila sem alterações e sem gerar nenhum aviso novo.</span><span class="sxs-lookup"><span data-stu-id="b1931-184">That decision means that your existing code compiles without changes and without generating any new warnings.</span></span>

<span data-ttu-id="b1931-185">As diferenças entre os contextos de aviso que permitem valor nulo `enabled` e `safeonly` são avisos para atribuir uma referência que permite valor nulo a uma referência que não permite valor nulo.</span><span class="sxs-lookup"><span data-stu-id="b1931-185">The differences between the `enabled` and `safeonly` nullable warning contexts are warnings for assigning a nullable reference to a non-nullable reference.</span></span> <span data-ttu-id="b1931-186">A atribuição a seguir gera um aviso em um contexto de aviso `enabled`, mas não um contexto de aviso `safeonly`.</span><span class="sxs-lookup"><span data-stu-id="b1931-186">The following assignment generates a warning in an `enabled` warning context, but not a `safeonly` warning context.</span></span> <span data-ttu-id="b1931-187">No entanto, a segunda linha, em que `s` é desreferenciado, gera um aviso em um contexto `safeonly`:</span><span class="sxs-lookup"><span data-stu-id="b1931-187">However, the second line, where `s` is dereferenced, generates a warning in a `safeonly` context:</span></span>

```csharp
string s = null; // warning when nullable warning context is enabled.
var txt = s.ToString(); // warning when nullable warnings context is safeonly, or enabled.
```

### <a name="nullable-annotation-context"></a><span data-ttu-id="b1931-188">Contexto de anotação que permite valor nulo</span><span class="sxs-lookup"><span data-stu-id="b1931-188">Nullable annotation context</span></span>

<span data-ttu-id="b1931-189">O compilador usa as seguintes regras em um contexto de anotação que permite valor nulo desabilitado:</span><span class="sxs-lookup"><span data-stu-id="b1931-189">The compiler uses the following rules in a disabled nullable annotation context:</span></span>

- <span data-ttu-id="b1931-190">Não é possível declarar referências que permitem valor nulo em um contexto desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b1931-190">You can't declare nullable references in a disabled context.</span></span>
- <span data-ttu-id="b1931-191">Todas as variáveis de referência podem ser atribuídas a nulo.</span><span class="sxs-lookup"><span data-stu-id="b1931-191">All reference variables may be assigned to null.</span></span>
- <span data-ttu-id="b1931-192">Nenhum aviso é gerado quando uma variável de um tipo de referência é desreferenciado.</span><span class="sxs-lookup"><span data-stu-id="b1931-192">No warnings are generated when a variable of a reference type is dereferenced.</span></span>
- <span data-ttu-id="b1931-193">O operador tolerante a nulo pode não ser usado em um contexto desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b1931-193">The null-forgiving operator may not be used in a disabled context.</span></span>

<span data-ttu-id="b1931-194">O comportamento é o mesmo que o das versões anteriores de C#.</span><span class="sxs-lookup"><span data-stu-id="b1931-194">The behavior is the same as previous versions of C#.</span></span>

<span data-ttu-id="b1931-195">O compilador usa as seguintes regras em um contexto de anotação que permite valor nulo habilitado:</span><span class="sxs-lookup"><span data-stu-id="b1931-195">The compiler uses the following rules in an enabled nullable annotation context:</span></span>

- <span data-ttu-id="b1931-196">Qualquer variável de um tipo de referência é uma **referência que não permite valor nulo**.</span><span class="sxs-lookup"><span data-stu-id="b1931-196">Any variable of a reference type is a **non-nullable reference**.</span></span>
- <span data-ttu-id="b1931-197">Qualquer referência que não permite valor nulo pode ser desreferenciada com segurança.</span><span class="sxs-lookup"><span data-stu-id="b1931-197">Any non-nullable reference may be dereferenced safely.</span></span>
- <span data-ttu-id="b1931-198">Qualquer tipo de referência que permite valor nulo (indicado pelo `?` após o tipo na declaração de variável) pode ser nulo.</span><span class="sxs-lookup"><span data-stu-id="b1931-198">Any nullable reference type (noted by `?` after the type in the variable declaration) may be null.</span></span> <span data-ttu-id="b1931-199">A análise estática determina se o valor é conhecido como não nulo quando ele é desreferenciado.</span><span class="sxs-lookup"><span data-stu-id="b1931-199">Static analysis determines if the value is known to be non-null when it is dereferenced.</span></span> <span data-ttu-id="b1931-200">Caso contrário, o compilador avisa.</span><span class="sxs-lookup"><span data-stu-id="b1931-200">If not, the compiler warns you.</span></span>
- <span data-ttu-id="b1931-201">É possível usar o operador tolerante a nulo para declarar que uma referência que permite valor nulo não é nula.</span><span class="sxs-lookup"><span data-stu-id="b1931-201">You can use the null-forgiving operator to declare that a nullable reference isn't null.</span></span>

<span data-ttu-id="b1931-202">Em um contexto de anotação que permite valor nulo habilitado, o caractere `?` acrescentado a um tipo de referência declara um **tipo de referência que permite valor nulo**.</span><span class="sxs-lookup"><span data-stu-id="b1931-202">In an enabled nullable annotation context, the `?` character appended to a reference type declares a **nullable reference type**.</span></span> <span data-ttu-id="b1931-203">O **operador de tolerância a nulo** (`!`) pode ser acrescentado a uma expressão para declarar que ela não é nula.</span><span class="sxs-lookup"><span data-stu-id="b1931-203">The **null forgiveness operator** (`!`) may be appended to an expression to declare that the expression isn't null.</span></span>

## <a name="nullable-warning-context"></a><span data-ttu-id="b1931-204">Contexto de aviso que permite valor nulo</span><span class="sxs-lookup"><span data-stu-id="b1931-204">Nullable warning context</span></span>

<span data-ttu-id="b1931-205">O contexto de aviso que permite valor nulo é diferente do contexto de anotação que permite valor nulo.</span><span class="sxs-lookup"><span data-stu-id="b1931-205">The nullable warning context is distinct from the nullable annotation context.</span></span> <span data-ttu-id="b1931-206">Os avisos podem ser habilitados mesmo quando as novas anotações estão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="b1931-206">Warnings can be enabled even when the new annotations are disabled.</span></span> <span data-ttu-id="b1931-207">O compilador usa a análise de fluxo estática para determinar o **estado nulo** de qualquer referência.</span><span class="sxs-lookup"><span data-stu-id="b1931-207">The compiler uses static flow analysis to determine the **null state** of any reference.</span></span> <span data-ttu-id="b1931-208">O estado nulo é **não nulo** ou **talvez nulo** quando o *contexto de aviso que permite valor nulo* não está **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="b1931-208">The null state is either **not null** or **maybe null** when the *nullable warning context* isn't **disabled**.</span></span> <span data-ttu-id="b1931-209">Se você desreferenciar uma referência quando o compilador tiver determinado que ela é **talvez nula**, o compilador avisará.</span><span class="sxs-lookup"><span data-stu-id="b1931-209">If you dereference a reference when the compiler has determined it's **maybe null**, the compiler warns you.</span></span> <span data-ttu-id="b1931-210">O estado de uma referência é **talvez nulo**, a menos que o compilador possa determinar uma das duas condições:</span><span class="sxs-lookup"><span data-stu-id="b1931-210">The state of a reference is **maybe null** unless the compiler can determine one of two conditions:</span></span>

1. <span data-ttu-id="b1931-211">A variável foi atribuída definitivamente a um valor não nulo.</span><span class="sxs-lookup"><span data-stu-id="b1931-211">The variable has been definitely assigned to a non-null value.</span></span>
1. <span data-ttu-id="b1931-212">A variável ou expressão foi marcada novamente como nula antes de desreferenciá-la.</span><span class="sxs-lookup"><span data-stu-id="b1931-212">The variable or expression has been checked against null before de-referencing it.</span></span>

<span data-ttu-id="b1931-213">O compilador gera avisos sempre que você desreferencia uma variável ou expressão em um estado **talvez nulo** quando o contexto de aviso que permite valor nulo é `enabled` ou `safeonly`.</span><span class="sxs-lookup"><span data-stu-id="b1931-213">The compiler generates warnings whenever you dereference a variable or expression in a **maybe null** state when the nullable warning context is `enabled` or `safeonly`.</span></span> <span data-ttu-id="b1931-214">Além disso, os avisos são gerados quando uma variável ou expressão **talvez nula** é atribuída a um tipo de referência que não permite valor nulo quando o contexto de anotação que permite valor nulo é `enabled`.</span><span class="sxs-lookup"><span data-stu-id="b1931-214">Furthermore, warnings are generated when a **maybe null** variable or expression is assigned to a nonnullable reference type when the nullable annotation context is `enabled`.</span></span>

## <a name="learn-more"></a><span data-ttu-id="b1931-215">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="b1931-215">Learn more</span></span>

- [<span data-ttu-id="b1931-216">Especificação de referência que permite valor nulo de rascunho</span><span class="sxs-lookup"><span data-stu-id="b1931-216">Draft Nullable reference specification</span></span>](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-8.0/nullable-reference-types-specification.md)
- [<span data-ttu-id="b1931-217">Introdução ao tutorial de referências que permitem valor nulo</span><span class="sxs-lookup"><span data-stu-id="b1931-217">Intro to nullable references tutorial</span></span>](tutorials/nullable-reference-types.md)
- [<span data-ttu-id="b1931-218">Migrar uma base de código para referências que permitem valor nulo</span><span class="sxs-lookup"><span data-stu-id="b1931-218">Migrate an existing codebase to nullable references</span></span>](tutorials/upgrade-to-nullable-references.md)