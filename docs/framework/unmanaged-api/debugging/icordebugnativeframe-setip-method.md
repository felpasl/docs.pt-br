---
title: "Método ICorDebugNativeFrame::SetIP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.SetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 563566a877d589ecd32575c095cdc812c28f6334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="7800e-102">Método ICorDebugNativeFrame::SetIP</span><span class="sxs-lookup"><span data-stu-id="7800e-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="7800e-103">Define o ponteiro de instrução para o local de deslocamento especificado em código nativo.</span><span class="sxs-lookup"><span data-stu-id="7800e-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7800e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7800e-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7800e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7800e-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="7800e-106">[in] O local de deslocamento no código nativo.</span><span class="sxs-lookup"><span data-stu-id="7800e-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7800e-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="7800e-107">Remarks</span></span>  
 <span data-ttu-id="7800e-108">Chamadas para `SetIP` imediatamente invalida todos os quadros e cadeias de para o thread atual.</span><span class="sxs-lookup"><span data-stu-id="7800e-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="7800e-109">Se o depurador precisa de informações de quadro após uma chamada para `SetIP`, ele deve realizar um novo rastreamento de pilha.</span><span class="sxs-lookup"><span data-stu-id="7800e-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="7800e-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) tentará manter o quadro de pilha em um estado válido.</span><span class="sxs-lookup"><span data-stu-id="7800e-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="7800e-111">No entanto, mesmo se o quadro estiver em um estado válido, que diz respeito o tempo de execução, ainda pode haver problemas, como variáveis locais não inicializadas e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="7800e-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="7800e-112">O chamador é responsável por garantir a coerência do programa em execução.</span><span class="sxs-lookup"><span data-stu-id="7800e-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="7800e-113">Em plataformas de 64 bits, o ponteiro de instrução não pode ser movido de um `catch` ou `finally` bloco.</span><span class="sxs-lookup"><span data-stu-id="7800e-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="7800e-114">Se `SetIP` é chamado para fazer isso em uma plataforma de 64 bits, será retornado um HRESULT indicando falha.</span><span class="sxs-lookup"><span data-stu-id="7800e-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7800e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7800e-115">Requirements</span></span>  
 <span data-ttu-id="7800e-116">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7800e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7800e-117">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7800e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7800e-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7800e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7800e-119">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7800e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7800e-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7800e-120">See Also</span></span>  
 