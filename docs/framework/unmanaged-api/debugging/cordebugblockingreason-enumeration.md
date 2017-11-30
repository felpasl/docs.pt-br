---
title: "Enumeração CorDebugBlockingReason"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugBlockingReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugBlockingReason
helpviewer_keywords: CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 505a83f15d5056b0280af31d372623530d6e66ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="390ca-102">Enumeração CorDebugBlockingReason</span><span class="sxs-lookup"><span data-stu-id="390ca-102">CorDebugBlockingReason Enumeration</span></span>
<span data-ttu-id="390ca-103">Especifica os motivos pelos quais um thread pode ficar bloqueado em um determinado objeto.</span><span class="sxs-lookup"><span data-stu-id="390ca-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="390ca-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="390ca-104">Syntax</span></span>  
  
```  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="390ca-105">Membros</span><span class="sxs-lookup"><span data-stu-id="390ca-105">Members</span></span>  
  
|<span data-ttu-id="390ca-106">Membro</span><span class="sxs-lookup"><span data-stu-id="390ca-106">Member</span></span>|<span data-ttu-id="390ca-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="390ca-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="390ca-108">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="390ca-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="390ca-109">Um thread está tentando adquirir a seção crítica que está associada ao monitor de bloqueio em um objeto.</span><span class="sxs-lookup"><span data-stu-id="390ca-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="390ca-110">Normalmente, isso ocorre quando você chama um do <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> ou <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> métodos.</span><span class="sxs-lookup"><span data-stu-id="390ca-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="390ca-111">Um thread está aguardando o evento que está associado um bloqueio de monitor para um objeto.</span><span class="sxs-lookup"><span data-stu-id="390ca-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="390ca-112">Normalmente, isso ocorre quando você chama um do <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` métodos.</span><span class="sxs-lookup"><span data-stu-id="390ca-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="390ca-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="390ca-113">Remarks</span></span>  
 <span data-ttu-id="390ca-114">Quando o `BLOCKING_MONITOR_CRITICAL_SECTION` ou `BLOCKING_MONITOR_EVENT` membro é usado em uma [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estrutura, o `pBlockingObject` membro dos pontos de estrutura a uma interface de "ICorDebugValue" que representa o objeto que está sendo inserido .</span><span class="sxs-lookup"><span data-stu-id="390ca-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="390ca-115">Também é garantido para implementar o [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="390ca-115">It is also guaranteed to implement the [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="390ca-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="390ca-116">Requirements</span></span>  
 <span data-ttu-id="390ca-117">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="390ca-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="390ca-118">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="390ca-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="390ca-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="390ca-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="390ca-120">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="390ca-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="390ca-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="390ca-121">See Also</span></span>  
 [<span data-ttu-id="390ca-122">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="390ca-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="390ca-123">Depuração</span><span class="sxs-lookup"><span data-stu-id="390ca-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)