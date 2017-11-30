---
title: "Exemplos de sintaxe da consulta com base em método: Ordenação (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8f791bdca34c49bf925af029d67883dbb49fc3b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="method-based-query-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="e7356-102">Exemplos de sintaxe da consulta com base em método: Ordenação (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="e7356-102">Method-Based Query Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="e7356-103">Os exemplos neste tópico demonstram como usar <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, e métodos de <xref:System.Linq.Enumerable.ThenBy%2A> para ver <xref:System.Data.DataSet> e para ordenar os resultados usando a sintaxe da consulta de método.</span><span class="sxs-lookup"><span data-stu-id="e7356-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>,  <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenBy%2A> methods to query a <xref:System.Data.DataSet> and order the results using the method query syntax.</span></span>  
  
 <span data-ttu-id="e7356-104">O `FillDataSet` método usado nesses exemplos é especificado em [carregar dados em um conjunto de dados](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="e7356-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="e7356-105">Os exemplos neste tópico usam as tabelas Contact, Address, Product, SalesOrderHeader e SalesOrderDetail no banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e7356-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e7356-106">Os exemplos neste tópico usam o seguinte `using` / `Imports` instruções:</span><span class="sxs-lookup"><span data-stu-id="e7356-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="e7356-107">Para obter mais informações, consulte [como: criar um LINQ to DataSet de projeto no Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e7356-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="e7356-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="e7356-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="e7356-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e7356-109">Example</span></span>  
 <span data-ttu-id="e7356-110">Este exemplo usa o método de <xref:System.Linq.Enumerable.OrderBy%2A> com um comparer personalizado para fazer o último nomes não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e7356-110">This example uses the <xref:System.Linq.Enumerable.OrderBy%2A> method with a custom comparer to do a case-insensitive sort of last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## <a name="reverse"></a><span data-ttu-id="e7356-111">Inverso</span><span class="sxs-lookup"><span data-stu-id="e7356-111">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="e7356-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e7356-112">Example</span></span>  
 <span data-ttu-id="e7356-113">Este exemplo usa o método de <xref:System.Linq.Enumerable.Reverse%2A> para criar uma lista de pedidos onde `OrderDate` for anterior do 20 de fevereiro de 2002.</span><span class="sxs-lookup"><span data-stu-id="e7356-113">This example uses the <xref:System.Linq.Enumerable.Reverse%2A> method to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenby"></a><span data-ttu-id="e7356-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="e7356-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="e7356-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e7356-115">Example</span></span>  
 <span data-ttu-id="e7356-116">Este exemplo usa <xref:System.Linq.Enumerable.OrderBy%2A> e métodos de <xref:System.Linq.Enumerable.ThenBy%2A> com um comparer personalizado para o primeiro tipo pelo custo de tabela em seguida, executa um sem diferenciação de maiúsculas e minúsculas descendo meio os nomes de produto.</span><span class="sxs-lookup"><span data-stu-id="e7356-116">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.ThenBy%2A> methods with a custom comparer to first sort by list price, and then perform a case-insensitive descending sort of the product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="e7356-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e7356-117">See Also</span></span>  
 [<span data-ttu-id="e7356-118">Carregar dados em um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="e7356-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="e7356-119">LINQ para exemplos de conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="e7356-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="e7356-120">Visão Geral de Operadores de Consulta Padrão</span><span class="sxs-lookup"><span data-stu-id="e7356-120">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)