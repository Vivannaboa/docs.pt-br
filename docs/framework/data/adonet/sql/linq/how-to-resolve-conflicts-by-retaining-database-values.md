---
title: 'Como: resolver conflitos mantendo valores de banco de dados'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
ms.openlocfilehash: 8440ffe61e254403357970d771aea207a6eb6092
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037655"
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a>Como: resolver conflitos mantendo valores de banco de dados
Para reconciliar diferenças entre valores esperados e reais de base de dados antes que você submeter tente novamente suas alterações, você pode usar <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> para manter os valores localizados na base de dados. Os valores atuais no modelo de objeto são substituídos em seguida. Para obter mais informações, consulte [a simultaneidade otimista: Visão geral do](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
> [!NOTE]
>  Em todos os casos, o registro no cliente é atualizado primeiro recuperando os dados atualizados de base de dados. Esta ação certifique-se de que a seguir tentativa de atualização não falhará nas mesmas verificação de simultaneidade.  
  
## <a name="example"></a>Exemplo  
 Nesse cenário, uma exceção é lançada de <xref:System.Data.Linq.ChangeConflictException> quando tenta User1 para enviar alterações, porque Usuário2 tiver alterado entretanto as colunas do assistente e departamento. A tabela a seguir mostra a situação.  
  
||Manager|Assistente|Departamento|  
|------|-------------|---------------|----------------|  
|Estado original de base de dados quando consultado por User1 e por Usuário2.|Alfreds|Maria|Vendas|  
|User1 prepara-se para enviar essas alterações.|Alfred||Marketing|  
|Usuário2 já tiver enviado essas alterações.||Mary|Serviço|  
  
 User1 decidir resolver esse conflito com os valores mais recentes de base de dados substitui os valores atuais no modelo de objeto.  
  
 Quando User1 resolver o conflito usando <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, o resultado na base de dados é o seguinte na tabela:  
  
||Manager|Assistente|Departamento|  
|------|-------------|---------------|----------------|  
|Novo estado após a resolução do conflito.|Alfreds<br /><br /> (original)|Mary<br /><br /> (de Usuário2)|Serviço<br /><br /> (de Usuário2)|  
  
 O código exemplo a seguir mostra como substituir valores atuais no modelo de objeto com os valores de base de dados. (Nenhuma inspeção ou manipulação personalizada de conflitos de membro individual ocorrem.)  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Consulte também

- [Como: Gerenciar conflitos de alteração](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
