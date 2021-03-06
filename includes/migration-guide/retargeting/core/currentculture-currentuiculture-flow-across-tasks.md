---
ms.openlocfilehash: efe8a2dd98865f6a24b65ce0f08eb0c574b708f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803153"
---
### <a name="currentculture-and-currentuiculture-flow-across-tasks"></a>Fluxo CurrentCulture e CurrentUICulture atravessam tarefas

|   |   |
|---|---|
|Detalhes|A partir do .NET Framework 4.6, <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> e <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> são armazenados no <xref:System.Threading.ExecutionContext?displayProperty=name> do thread, que atravessa operações assíncronas. Isso significa que as alterações em <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> ou <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> serão refletidas em tarefas que posteriormente serão executadas de forma assíncrona. Isso é diferente do comportamento das versões anteriores do .NET Framework (que redefiniria <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> e <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> em todas as tarefas assíncronas).|
|Sugestão|Aplicativos afetados por essa alteração podem contorná-la definindo explicitamente o <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> ou <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> desejado como a primeira operação em uma Tarefa assíncrona. Como alternativa, o comportamento antigo (de não atravessar <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name>) pode ser aceito definindo a seguinte opção de compatibilidade:<pre><code class="lang-csharp">AppContext.SetSwitch(&quot;Switch.System.Globalization.NoAsyncCurrentCulture&quot;, true);&#13;&#10;</code></pre>Esse problema foi corrigido pelo WPF no .NET Framework 4.6.2. Ele também foi corrigido no .NET Framework 4.6 e 4.6.1 por meio de [KB 3139549](https://support.microsoft.com/kb/3139549). Os aplicativos direcionados ao .NET Framework 4.6 ou posterior terão o comportamento correto automaticamente nos aplicativos WPF – <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name>. Isso seria preservado entre as operações de Dispatcher.|
|Escopo|Secundário|
|Versão|4.6|
|Tipo|Redirecionando|
|APIs afetadas|<ul><li><xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType></li><li><xref:System.Threading.Thread.CurrentCulture?displayProperty=nameWithType></li><li><xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=nameWithType></li><li><xref:System.Threading.Thread.CurrentUICulture?displayProperty=nameWithType></li></ul>|
