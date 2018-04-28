### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="d4255-101">RSACng.VerifyHash agora retorna False para qualquer falha de verificação</span><span class="sxs-lookup"><span data-stu-id="d4255-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d4255-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d4255-102">Details</span></span>|<span data-ttu-id="d4255-103">A partir do .NET Framework 4.6.2, esse método retornará <strong>False</strong> se a assinatura em si estiver incorretamente formatada.</span><span class="sxs-lookup"><span data-stu-id="d4255-103">Starting with the .NET Framework 4.6.2, this method returns <strong>False</strong> if the signature itself is badly formatted.</span></span> <span data-ttu-id="d4255-104">Agora, ele retornará false para qualquer falha de verificação. No .NET Framework 4.6 e 4.6.1, o método gera <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> se a assinatura em si está incorretamente formatada.</span><span class="sxs-lookup"><span data-stu-id="d4255-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="d4255-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="d4255-105">Suggestion</span></span>|<span data-ttu-id="d4255-106">Qualquer código cuja execução dependa da identificação de <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> deverá ser executado se a validação falhar e o método retornar <strong>False</strong>.</span><span class="sxs-lookup"><span data-stu-id="d4255-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns <strong>False</strong>.</span></span>|
|<span data-ttu-id="d4255-107">Escopo</span><span class="sxs-lookup"><span data-stu-id="d4255-107">Scope</span></span>|<span data-ttu-id="d4255-108">Secundário</span><span class="sxs-lookup"><span data-stu-id="d4255-108">Minor</span></span>|
|<span data-ttu-id="d4255-109">Versão</span><span class="sxs-lookup"><span data-stu-id="d4255-109">Version</span></span>|<span data-ttu-id="d4255-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d4255-110">4.6.2</span></span>|
|<span data-ttu-id="d4255-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="d4255-111">Type</span></span>|<span data-ttu-id="d4255-112">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="d4255-112">Runtime</span></span>|
|<span data-ttu-id="d4255-113">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="d4255-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
