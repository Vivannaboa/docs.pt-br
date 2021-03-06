---
title: Modificar dados com um DbDataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e35c7f9e-648b-4fcc-9361-d365c3e42c9a
ms.openlocfilehash: 3038e35947cd8f97266d374a367a77380df440dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772171"
---
# <a name="modifying-data-with-a-dbdataadapter"></a>Modificar dados com um DbDataAdapter
O <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> método de um <xref:System.Data.Common.DbProviderFactory> objeto lhe dá um <xref:System.Data.Common.DbDataAdapter> objeto fortemente tipado para o provedor de dados subjacente especificado no momento em que você cria a fábrica. Você pode usar um <xref:System.Data.Common.DbCommandBuilder> para criar comandos para inserir, atualizar e excluir dados de um <xref:System.Data.DataSet> para uma fonte de dados.  
  
## <a name="retrieving-data-with-a-dbdataadapter"></a>Recuperação de dados com um DbDataAdapter  
 Este exemplo demonstra como criar um com rigidez de tipos `DbDataAdapter` com base em uma cadeia de caracteres de nome e a conexão de provedor. O código usa o <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> método da <xref:System.Data.Common.DbProviderFactory> para criar um <xref:System.Data.Common.DbConnection>. Em seguida, o código usa o <xref:System.Data.Common.DbProviderFactory.CreateCommand%2A> método para criar um <xref:System.Data.Common.DbCommand> para selecionar dados definindo sua `CommandText` e `Connection` propriedades. Por fim, o código cria uma <xref:System.Data.Common.DbDataAdapter> objeto usando o <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> método e define seu `SelectCommand` propriedade. O `Fill` método da `DbDataAdapter` carrega os dados em um <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/VB/source.vb#1)]  
  
## <a name="modifying-data-with-a-dbdataadapter"></a>Modificar dados com um DbDataAdapter  
 Este exemplo demonstra como modificar dados em um `DataTable` usando um <xref:System.Data.Common.DbDataAdapter> usando um <xref:System.Data.Common.DbCommandBuilder> para gerar os comandos necessários para a atualização de dados na fonte de dados. O <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> do `DbDataAdapter` é definido para recuperar o CustomerID e CompanyName da tabela Customers. O <xref:System.Data.Common.DbCommandBuilder.GetInsertCommand%2A> método é usado para definir o <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A> propriedade, o <xref:System.Data.Common.DbCommandBuilder.GetUpdateCommand%2A> método é usado para definir a <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> propriedade e o <xref:System.Data.Common.DbCommandBuilder.GetDeleteCommand%2A> método é usado para definir o <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> propriedade. O código adiciona uma nova linha à tabela clientes e atualiza a fonte de dados. O código, em seguida, localiza a linha adicionada pesquisando em CustomerID, que é a chave primária definida para a tabela Customers. Ele altera o CompanyName e atualiza a fonte de dados. Por fim, o código exclui a linha.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/VB/source.vb#1)]  
  
## <a name="handling-parameters"></a>Manipulando parâmetros  
 Os provedores de dados .NET Framework lidar com a nomenclatura e especificando parâmetros e espaços reservados de parâmetro de forma diferente. Essa sintaxe é adaptada a uma fonte de dados específicos, conforme descrito na tabela a seguir.  
  
|Provedor de dados|Sintaxe de nomeação de parâmetro|  
|-------------------|-----------------------------|  
|`SqlClient`|Usa parâmetros nomeados no formato `@` *parametername*.|  
|`OracleClient`|Usa parâmetros nomeados no formato `:` *parmname* (ou *parmname*).|  
|`OleDb`|Usa os marcadores de parâmetros posicionais indicados por um ponto de interrogação (`?`).|  
|`Odbc`|Usa os marcadores de parâmetros posicionais indicados por um ponto de interrogação (`?`).|  
  
 O modelo de fábrica não é útil para a criação de parametrizada `DbCommand` e `DbDataAdapter` objetos. Você precisará de ramificação em seu código para criar parâmetros de acordo com seu provedor de dados.  
  
> [!IMPORTANT]
>  Evitar parâmetros específicos do provedor completamente usando concatenação de cadeia de caracteres para construir instruções diretas do SQL não é recomendável por razões de segurança. Usando a concatenação de cadeia de caracteres em vez de parâmetros vulnerável a ataques de injeção de SQL de seu aplicativo.  
  
## <a name="see-also"></a>Consulte também

- [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)
- [Obtendo um DbProviderFactory](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)
- [DbConnection, DbCommand e DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)
- [ADO.NET Managed Providers and DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)
