---
title: "Ação bloqueado de exceção de instância"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 164a5419-315c-4987-ad72-54cbdb88d402
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6a5a0d805d5c8cbae67b97afa220ad769179e198
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="instance-locked-exception-action"></a><span data-ttu-id="11a61-102">Ação bloqueado de exceção de instância</span><span class="sxs-lookup"><span data-stu-id="11a61-102">Instance Locked Exception Action</span></span>
<span data-ttu-id="11a61-103">A propriedade de <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A> de instância Store de fluxo de trabalho do SQL permite que você especifique que ação o provedor de persistência do SQL deve tomar quando ele recebe <xref:System.Runtime.DurableInstancing.InstanceLockedException>.</span><span class="sxs-lookup"><span data-stu-id="11a61-103">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A> property of the SQL Workflow Instance Store lets you specify what action the SQL persistence provider should take when it receives an <xref:System.Runtime.DurableInstancing.InstanceLockedException>.</span></span> <span data-ttu-id="11a61-104">O provedor de persistência recebe esta exceção quando tentar bloquear uma instância do serviço de fluxo de trabalho que está atualmente bloqueada por outro host serviço.</span><span class="sxs-lookup"><span data-stu-id="11a61-104">The persistence provider receives this exception when it tries to lock a workflow service instance that is currently locked by another service host.</span></span> <span data-ttu-id="11a61-105">Os valores para essa propriedade é <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>, <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry>, e <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>.</span><span class="sxs-lookup"><span data-stu-id="11a61-105">The values for this property are <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>, <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry>, and <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>.</span></span> <span data-ttu-id="11a61-106">O valor padrão é <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>.</span><span class="sxs-lookup"><span data-stu-id="11a61-106">The default value is <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>.</span></span> <span data-ttu-id="11a61-107">A lista a seguir descreve as três opções:</span><span class="sxs-lookup"><span data-stu-id="11a61-107">The following list describes the three options:</span></span>  
  
-   <span data-ttu-id="11a61-108"><xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>.</span><span class="sxs-lookup"><span data-stu-id="11a61-108"><xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>.</span></span> <span data-ttu-id="11a61-109">O host de serviço não tenta bloquear a instância do serviço de fluxo de trabalho e passa o <xref:System.Runtime.DurableInstancing.InstanceLockedException> ao chamador.</span><span class="sxs-lookup"><span data-stu-id="11a61-109">The service host does not attempt to lock the workflow service instance and passes the <xref:System.Runtime.DurableInstancing.InstanceLockedException> to the caller.</span></span>  <span data-ttu-id="11a61-110">Se o fluxo de trabalho permanece na memória por um período exceder 60 segundos, use <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry> como a repetição.</span><span class="sxs-lookup"><span data-stu-id="11a61-110">If your workflow stays in memory for a period exceeding 60 seconds, use <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry> as the retry.</span></span> <span data-ttu-id="11a61-111">O valor padrão é <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>.</span><span class="sxs-lookup"><span data-stu-id="11a61-111">The default value is <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>.</span></span>  
  
-   <span data-ttu-id="11a61-112"><xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry>.</span><span class="sxs-lookup"><span data-stu-id="11a61-112"><xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry>.</span></span> <span data-ttu-id="11a61-113">Os reattempts de host serviço para bloquear a instância do serviço de fluxo de trabalho com um intervalo linear entre a nova tentativa tentam e passam <xref:System.Runtime.DurableInstancing.InstanceLockedException> para o chamador no final da sequência.</span><span class="sxs-lookup"><span data-stu-id="11a61-113">The service host reattempts to lock the workflow service instance with a linear interval between retry attempts and passes the <xref:System.Runtime.DurableInstancing.InstanceLockedException> to the caller at the end of the sequence.</span></span> <span data-ttu-id="11a61-114">Se você fluxo de trabalho permanece na memória aproximadamente entre 5-60 segundos, e mensagens chegue em lotes onde é mais provável para as mensagens que estão sendo enviadas para a mesma instância no mesmo host para processar as mensagens antes de descarregar o fluxo de trabalho, use <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> para obter melhor latência sem desperdiçar recursos.</span><span class="sxs-lookup"><span data-stu-id="11a61-114">If you workflow stays in memory approximately between 5-60 seconds, and messages arrive in batches where it is more likely for messages being sent to the same instance on the same host to process all messages before unloading the workflow, use <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> to achieve the best latency without wasting resources.</span></span>  
  
-   <span data-ttu-id="11a61-115"><xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>.</span><span class="sxs-lookup"><span data-stu-id="11a61-115"><xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>.</span></span> <span data-ttu-id="11a61-116">Os reattempts de host serviço para bloquear a instância do serviço de fluxo de trabalho com um intervalo exponencialmente de backoff entre a nova tentativa tentam, e passe a exceção para o chamador no final da sequência.</span><span class="sxs-lookup"><span data-stu-id="11a61-116">The service host reattempts to lock the workflow service instance with an exponential backoff interval between retry attempts, and passes the exception to the caller at the end of the sequence.</span></span> <span data-ttu-id="11a61-117">Se seu fluxo de trabalho permanece na memória por muito um tempo abreviado (menos de 5 segundos), ou uma Web farm é grande e a possibilidade de outra mensagem que está sendo entregada ao mesmo host não é muito alta, usa <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry> para obter melhor latência.</span><span class="sxs-lookup"><span data-stu-id="11a61-117">If your workflow stays in memory for a very short time (less than 5 seconds), or a Web farm is large and the chance of another message being delivered to the same host is not very high, use <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry> to achieve the best latency.</span></span>  
  
 <span data-ttu-id="11a61-118">O recurso protegido instância de ação de exceção oferece suporte aos seguintes cenários.</span><span class="sxs-lookup"><span data-stu-id="11a61-118">The Instance Locked Exception Action feature supports the following scenarios.</span></span> <span data-ttu-id="11a61-119">Em todos os cenários, se a propriedade de instanceLockedExceptionAction de SqlWorkflowInstanceStore é definida como <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> ou a <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>, o host tentar de novo transparente para adquirir periodicamente o bloqueio em instâncias.</span><span class="sxs-lookup"><span data-stu-id="11a61-119">In all scenarios, if the instanceLockedExceptionAction property of the SqlWorkflowInstanceStore is set to <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> or <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>, the host transparently retries to acquire the lock on instances periodically.</span></span>  
  
1.  <span data-ttu-id="11a61-120">**Habilitando o desligamento normal e reciclagem sobreposta de domínios de aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="11a61-120">**Enabling graceful shutdown and overlapped recycling of application domains.**</span></span> <span data-ttu-id="11a61-121">Suponha que um **AppDomain** com um host de serviço executando instâncias do serviço de fluxo de trabalho está sendo reciclado e um novo **AppDomain** ativados para lidar com novas solicitações em paralelo, enquanto o antigo  **AppDomain** seja interrompido normalmente.</span><span class="sxs-lookup"><span data-stu-id="11a61-121">Suppose an **AppDomain** with a service host running workflow service instances is being recycled and a new **AppDomain** is brought up to handle new requests in parallel while the old **AppDomain** is brought down gracefully.</span></span> <span data-ttu-id="11a61-122">O desligamento espera até que as instâncias de serviço de fluxo de trabalho são ociosos, e então descarrega e persistir as instâncias.</span><span class="sxs-lookup"><span data-stu-id="11a61-122">The shutdown waits until workflow service instances are idle, and then persists and unloads the instances.</span></span> <span data-ttu-id="11a61-123">Qualquer tentativa de hosts no novo **AppDomain** bloquear uma instância fará com que um <xref:System.Runtime.DurableInstancing.InstanceLockedException>.</span><span class="sxs-lookup"><span data-stu-id="11a61-123">Any attempts by hosts in the new **AppDomain** to lock an instance will cause an <xref:System.Runtime.DurableInstancing.InstanceLockedException>.</span></span>  
  
2.  <span data-ttu-id="11a61-124">**Dimensionamento horizontalmente duráveis fluxos de trabalho em um farm homogêneo de servidores.**</span><span class="sxs-lookup"><span data-stu-id="11a61-124">**Horizontally scaling durable workflows across a homogeneous farm of servers.**</span></span> <span data-ttu-id="11a61-125">Suponha que um nó de um farm de servidores em que uma instância de fluxo de trabalho está executando falhas e o host de fluxo de trabalho não pode remover os bloqueios na instância que está executando.</span><span class="sxs-lookup"><span data-stu-id="11a61-125">Suppose a node of a server farm on which a workflow instance is running crashes and the workflow host cannot remove locks on the instance it is running.</span></span> <span data-ttu-id="11a61-126">Quando uma execução do host serviço em outro nó de farm recebe uma mensagem para essa instância do fluxo de trabalho, tentar adquirir bloqueios nessas instâncias que receberá <xref:System.Runtime.DurableInstancing.InstanceLockedException>.</span><span class="sxs-lookup"><span data-stu-id="11a61-126">When a service host running on another node of the farm receives a message for that workflow instance, it tries to acquire locks on these instances it will receive the <xref:System.Runtime.DurableInstancing.InstanceLockedException>.</span></span> <span data-ttu-id="11a61-127">Os bloqueios expirarão após algum tempo porque o host que foi suponha renovar o bloqueio ainda não existir.</span><span class="sxs-lookup"><span data-stu-id="11a61-127">The locks will expire after some time because the host that was supposed to renew the lock no longer exists.</span></span>  
  
     <span data-ttu-id="11a61-128">**Dimensionamento horizontalmente duráveis fluxos de trabalho em um farm homogêneo de servidores.**</span><span class="sxs-lookup"><span data-stu-id="11a61-128">**Horizontally scaling durable workflows across a homogeneous farm of servers.**</span></span>  <span data-ttu-id="11a61-129">Suponha que você deseja dimensionar horizontalmente um fluxo de trabalho durável usando vários hosts por trás de um NLB (balanceador de carga de rede), o host de fluxo de trabalho em execução em um nó do farm carrega uma instância de fluxo de trabalho e está processando uma mensagem e a próxima mensagem para a instância é roteada para o host está em execução em outro nó porque o NLB não tem o algoritmo de roteamento para entregar as mensagens para o host que já está executando a instância.</span><span class="sxs-lookup"><span data-stu-id="11a61-129">Suppose you want to horizontally scale a durable workflow using multiple hosts behind a NLB (Network Load Balancer), the workflow host running on one node of the farm loads a workflow instance and is processing a message, and the next message to the instance is routed to the host that is running on another node because the NLB does not have routing algorithm to deliver messages to the host that is already running the instance.</span></span> <span data-ttu-id="11a61-130">Em cima de receber a mensagem, a segunda tentativas de host de carregar a instância de fluxo de trabalho e recebem <xref:System.Runtime.DurableInstancing.InstanceLockedException> porque o primeiro host tem um bloqueio na instância.</span><span class="sxs-lookup"><span data-stu-id="11a61-130">Upon receiving the message, the second host attempts to load the workflow instance and receives the <xref:System.Runtime.DurableInstancing.InstanceLockedException> because the first host has a lock on the instance.</span></span> <span data-ttu-id="11a61-131">O primeiro host desbloqueia a instância quando estiver concluído processamento com a primeira mensagem e o segundo host adquire o bloqueio quando tentar novamente a próxima vez, carregar a instância, e processa a segunda mensagem.</span><span class="sxs-lookup"><span data-stu-id="11a61-131">The first host unlocks the instance when it is finished with processing the first message and the second host acquires the lock when it retries the next time, loads the instance, and processes the second message.</span></span>