---
title: "Método ICorDebugValue::GetType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue.GetType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d214da529aed40d33bdf18530560e9cd7b00f60a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="dbce0-102">Método ICorDebugValue::GetType</span><span class="sxs-lookup"><span data-stu-id="dbce0-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="dbce0-103">Obtém o tipo primitivo do objeto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="dbce0-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbce0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dbce0-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbce0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="dbce0-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="dbce0-106">[out] Um ponteiro para um valor da enumeração "CorElementType" que indica o tipo do valor.</span><span class="sxs-lookup"><span data-stu-id="dbce0-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbce0-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="dbce0-107">Remarks</span></span>  
 <span data-ttu-id="dbce0-108">Se o objeto for um tipo complexo de tempo de execução, esse tipo pode ser examinado por meio das subclasses apropriadas a `ICorDebugValue` interface.</span><span class="sxs-lookup"><span data-stu-id="dbce0-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="dbce0-109">Por exemplo, "ICorDebugObjectValue", que herda de `ICorDebugValue`, representa um tipo complexo.</span><span class="sxs-lookup"><span data-stu-id="dbce0-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="dbce0-110">O `GetType` e [Icordebugobjectvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) métodos retornam informações sobre o tipo de um valor.</span><span class="sxs-lookup"><span data-stu-id="dbce0-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="dbce0-111">Elas são substituídas pelas com reconhecimento de genéricos [Icordebugvalue2](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="dbce0-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbce0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbce0-112">Requirements</span></span>  
 <span data-ttu-id="dbce0-113">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbce0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbce0-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbce0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbce0-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbce0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbce0-116">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbce0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbce0-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="dbce0-117">See Also</span></span>  
 