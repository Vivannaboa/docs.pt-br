---
title: 'Como: enviar alterações para o banco de dados'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c7cba174-9d40-491d-b32c-f2d73b7e9eab
ms.openlocfilehash: 222ce575d9e977cc8b68862385b4a1b147c6394a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902688"
---
# <a name="how-to-submit-changes-to-the-database"></a>Como: enviar alterações para o banco de dados
Independentemente de quantas você faz alterações aos objetos, as alterações são feitas somente para réplicas de memória. Você não tiver nenhuma alteração nos dados reais na base de dados. Suas alterações não são passadas para o servidor até que você chama explicitamente <xref:System.Data.Linq.DataContext.SubmitChanges%2A> em <xref:System.Data.Linq.DataContext>.  
  
 Quando você fizer essa chamada, <xref:System.Data.Linq.DataContext> tenta converter suas alterações em comandos SQL equivalentes. Você pode usar sua própria lógica personalizada para substituir essas ações, mas a ordem de envio é orquestrada por um serviço do <xref:System.Data.Linq.DataContext> conhecido como o *alterar processador*. A sequência de eventos é a seguinte:  
  
1. Quando você chama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] examina o conjunto de objetos conhecidos para determinar se as novas instâncias eles foram anexadas. Se eles tiverem, essas novas instâncias são adicionadas ao conjunto de objetos rastreadas.  
  
2. Todos os objetos que possuem durante alterações são ordenados em uma sequência de objetos com base nas dependências entre eles. Os objetos cujas ambas as alterações depende de outros objetos são arranjados seqüencialmente após as suas dependências.  
  
3. Imediatamente antes todas as alterações reais são passadas, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] inicia uma transação para encapsular a série de comandos individuais.  
  
4. As alterações para os objetos são traduzidas um por um para comandos SQL e enviadas ao servidor.  
  
 Neste ponto, todos os erros detectados por base de dados fazem com que o processo de envio parar, e uma exceção é gerada. Todas as alterações a base de dados são revertidas como se nenhuma envio ocorreu nunca. <xref:System.Data.Linq.DataContext> ainda tem uma gravação completa de todas as alterações. Portanto você pode tentar corrigir o problema e chamar novamente <xref:System.Data.Linq.DataContext.SubmitChanges%2A> , como no exemplo de código que segue.  
  
## <a name="example"></a>Exemplo  
 Quando a transação em torno do envio é concluída com êxito, <xref:System.Data.Linq.DataContext> aceita as alterações aos objetos ignorando as informações de controle de alterações.  
  
 [!code-csharp[DLinqSubmittingChanges#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#1)]
 [!code-vb[DLinqSubmittingChanges#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Consulte também

- [Como: Detectar e resolver submissões conflitantes](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)
- [Como: Gerenciar conflitos de alteração](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md) (Baixando bancos de dados de amostra)
- [Realizando e enviando alterações de dados](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
