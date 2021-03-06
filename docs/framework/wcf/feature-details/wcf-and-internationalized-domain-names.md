---
title: WCF e nomes de domínio internacionalizados
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: c53c22e388ec352b1275018c0b945c9608565084
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932516"
---
# <a name="wcf-and-internationalized-domain-names"></a>WCF e nomes de domínio internacionalizados
Foi adicionado suporte para permitir que os serviços WCF com nomes de domínio internacionalizado (IDN). Um nome de domínio internacionalizados é um nome de domínio que contém caracteres não ASCII. Esse suporte inclui a capacidade de hospedar um serviço WCF com um nome IDN e um cliente WCF para se comunicar com um serviço web com um nome IDN.  
  
## <a name="systemuri-and-idn"></a>System. URI e a IDN  
 <xref:System.Uri> tem duas propriedades <xref:System.Uri.Host%2A> e <xref:System.Uri.DnsSafeHost%2A>. Essas propriedades contêm valores Unicode ou Punycode dependendo das configurações de configuração de IDN.  
  
 IDN estar habilitado no arquivo de configuração de um aplicativo usando o seguinte XML  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 O \<idn > elemento contém o atributo habilitado, que pode ser definido como um dos seguintes valores:  
  
1. "None"  
  
2. "AllExceptIntranet"  
  
3. "Tudo"  
  
 Quando a configuração de IDN é definida como "None", nenhuma conversão é realizada pelo URI ou DnsSafeHost. Quando a configuração de IDN é definida como "All", do uri. Host permanece Unicode e uri. DnsSafeHost é convertido em Punycode. Quando a configuração de IDN é definida como "AllExceptIntranet", o uri. DnsSafeHost é convertido em Punycode para endereços da internet e permanece Unicode para endereços da intranet. Essa configuração é importante para a resolução de nome DNS correta. Observe que essa configuração não é necessário para ser configurado para o Windows 8 e versões mais recentes.  
  
> [!WARNING]
>  Você deve nunca embutir um endereço usando Punycode. WCF irá convertê-lo para você com base nas definições de configuração que se aplicam.  
  
> [!WARNING]
>  Ao adicionar caracteres Unicode a applicationHost.exe.config, salve o arquivo usando a codificação UTF-8.  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Uri?displayProperty=nameWithType>
