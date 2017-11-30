---
title: "Método ICorDebugMDA::GetOSThreadId"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetOSThreadId
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6cc53eecadd982d7cea045424de52d8e6f64107b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="b9b5a-102">Método ICorDebugMDA::GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="b9b5a-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="b9b5a-103">Obtém o identificador de thread do sistema operacional (SO) no qual o Assistente de depuração gerenciado (MDA) representado por [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) está em execução.</span><span class="sxs-lookup"><span data-stu-id="b9b5a-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b5a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b9b5a-104">Syntax</span></span>  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9b5a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b9b5a-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="b9b5a-106">[out] Um ponteiro para o identificador de thread do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="b9b5a-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9b5a-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="b9b5a-107">Remarks</span></span>  
 <span data-ttu-id="b9b5a-108">O thread de sistema operacional é usado em vez de um ICorDebugThread para situações em que um MDA é acionado em um thread nativo ou em um thread gerenciado que ainda não tiver inserido o código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="b9b5a-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9b5a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9b5a-109">Requirements</span></span>  
 <span data-ttu-id="b9b5a-110">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9b5a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9b5a-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9b5a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9b5a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9b5a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9b5a-113">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9b5a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b5a-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b9b5a-114">See Also</span></span>  
 [<span data-ttu-id="b9b5a-115">Interface ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="b9b5a-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="b9b5a-116">Diagnosticando erros com Assistentes de Depuração Gerenciados</span><span class="sxs-lookup"><span data-stu-id="b9b5a-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)