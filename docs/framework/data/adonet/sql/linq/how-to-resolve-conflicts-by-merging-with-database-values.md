---
title: 'Como: Resolver Conflitos mesclando com valores de base de dados'
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
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8e5114052951950c5866d80c974555678b1d040a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a><span data-ttu-id="8c2b7-102">Como: Resolver Conflitos mesclando com valores de base de dados</span><span class="sxs-lookup"><span data-stu-id="8c2b7-102">How to: Resolve Conflicts by Merging with Database Values</span></span>
<span data-ttu-id="8c2b7-103">Para reconciliar diferenças entre valores esperados e reais de base de dados antes que você submeter tente novamente suas alterações, você pode usar <xref:System.Data.Linq.RefreshMode.KeepChanges> para mesclar valores de base de dados com os valores atuais do membro de cliente.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepChanges> to merge database values with the current client member values.</span></span> <span data-ttu-id="8c2b7-104">Para obter mais informações, consulte [simultaneidade otimista: Visão geral do](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8c2b7-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c2b7-105">Em todos os casos, o registro no cliente é atualizado primeiro recuperando os dados atualizados de base de dados.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="8c2b7-106">Esta ação certifique-se de que a seguir tentativa de atualização não falhará nas mesmas verificação de simultaneidade.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c2b7-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8c2b7-107">Example</span></span>  
 <span data-ttu-id="8c2b7-108">Nesse cenário, uma exceção é lançada de <xref:System.Data.Linq.ChangeConflictException> quando tenta User1 para enviar alterações, porque Usuário2 tiver alterado entretanto as colunas do assistente e departamento.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-108">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="8c2b7-109">A tabela a seguir mostra a situação.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="8c2b7-110">Manager</span><span class="sxs-lookup"><span data-stu-id="8c2b7-110">Manager</span></span>|<span data-ttu-id="8c2b7-111">Assistente</span><span class="sxs-lookup"><span data-stu-id="8c2b7-111">Assistant</span></span>|<span data-ttu-id="8c2b7-112">Departamento</span><span class="sxs-lookup"><span data-stu-id="8c2b7-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="8c2b7-113">Estado original de base de dados quando consultado por User1 e por Usuário2.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="8c2b7-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="8c2b7-114">Alfreds</span></span>|<span data-ttu-id="8c2b7-115">Maria</span><span class="sxs-lookup"><span data-stu-id="8c2b7-115">Maria</span></span>|<span data-ttu-id="8c2b7-116">Vendas</span><span class="sxs-lookup"><span data-stu-id="8c2b7-116">Sales</span></span>|  
|<span data-ttu-id="8c2b7-117">User1 prepara-se para enviar essas alterações.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="8c2b7-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="8c2b7-118">Alfred</span></span>||<span data-ttu-id="8c2b7-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="8c2b7-119">Marketing</span></span>|  
|<span data-ttu-id="8c2b7-120">Usuário2 já tiver enviado essas alterações.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="8c2b7-121">Mary</span><span class="sxs-lookup"><span data-stu-id="8c2b7-121">Mary</span></span>|<span data-ttu-id="8c2b7-122">Serviço</span><span class="sxs-lookup"><span data-stu-id="8c2b7-122">Service</span></span>|  
  
 <span data-ttu-id="8c2b7-123">User1 decidir resolver esse conflito de mesclagem valores base de dados com os valores atuais do membro de cliente.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-123">User1 decides to resolve this conflict by merging database values with the current client member values.</span></span> <span data-ttu-id="8c2b7-124">O resultado é que os valores de base de dados são substituídos somente quando o conjunto de alterações atual também alterou o valor.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-124">The result will be that database values are overwritten only when the current changeset has also modified that value.</span></span>  
  
 <span data-ttu-id="8c2b7-125">Quando User1 resolver o conflito usando <xref:System.Data.Linq.RefreshMode.KeepChanges>, o resultado na base de dados é como na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="8c2b7-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepChanges>, the result in the database is as in the following table:</span></span>  
  
||<span data-ttu-id="8c2b7-126">Manager</span><span class="sxs-lookup"><span data-stu-id="8c2b7-126">Manager</span></span>|<span data-ttu-id="8c2b7-127">Assistente</span><span class="sxs-lookup"><span data-stu-id="8c2b7-127">Assistant</span></span>|<span data-ttu-id="8c2b7-128">Departamento</span><span class="sxs-lookup"><span data-stu-id="8c2b7-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="8c2b7-129">Novo estado após a resolução do conflito.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-129">New state after conflict resolution.</span></span>|<span data-ttu-id="8c2b7-130">Alfred</span><span class="sxs-lookup"><span data-stu-id="8c2b7-130">Alfred</span></span><br /><br /> <span data-ttu-id="8c2b7-131">(de User1)</span><span class="sxs-lookup"><span data-stu-id="8c2b7-131">(from User1)</span></span>|<span data-ttu-id="8c2b7-132">Mary</span><span class="sxs-lookup"><span data-stu-id="8c2b7-132">Mary</span></span><br /><br /> <span data-ttu-id="8c2b7-133">(de Usuário2)</span><span class="sxs-lookup"><span data-stu-id="8c2b7-133">(from User2)</span></span>|<span data-ttu-id="8c2b7-134">Marketing</span><span class="sxs-lookup"><span data-stu-id="8c2b7-134">Marketing</span></span><br /><br /> <span data-ttu-id="8c2b7-135">(de User1)</span><span class="sxs-lookup"><span data-stu-id="8c2b7-135">(from User1)</span></span>|  
  
 <span data-ttu-id="8c2b7-136">O exemplo a seguir mostra como mesclar valores de base de dados com os valores atuais do membro de cliente (a menos que o cliente também alterou o valor).</span><span class="sxs-lookup"><span data-stu-id="8c2b7-136">The following example shows how to merge database values with the current client member values (unless the client has also changed that value).</span></span> <span data-ttu-id="8c2b7-137">Nenhuma inspeção ou manipulação personalizada de conflitos de membro individual ocorrem.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-137">No inspection or custom handling of individual member conflicts occurs.</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8c2b7-138">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8c2b7-138">See Also</span></span>  
 [<span data-ttu-id="8c2b7-139">Como: resolver conflitos substituindo valores de banco de dados</span><span class="sxs-lookup"><span data-stu-id="8c2b7-139">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 [<span data-ttu-id="8c2b7-140">Como: resolver conflitos mantendo valores de banco de dados</span><span class="sxs-lookup"><span data-stu-id="8c2b7-140">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 [<span data-ttu-id="8c2b7-141">Como: gerenciar conflitos de alteração</span><span class="sxs-lookup"><span data-stu-id="8c2b7-141">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)