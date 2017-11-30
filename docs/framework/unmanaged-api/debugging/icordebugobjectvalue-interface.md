---
title: ICorDebugObjectValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue
helpviewer_keywords: ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: acbfbbb8f7374b1ab783371d318bd3bcf89963fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugobjectvalue-interface1"></a><span data-ttu-id="0dff9-102">ICorDebugObjectValue Interface1</span><span class="sxs-lookup"><span data-stu-id="0dff9-102">ICorDebugObjectValue Interface1</span></span>
<span data-ttu-id="0dff9-103">Uma subclasse de "ICorDebugValue" que representa um valor que contém um objeto.</span><span class="sxs-lookup"><span data-stu-id="0dff9-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0dff9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0dff9-104">Methods</span></span>  
  
|<span data-ttu-id="0dff9-105">Método</span><span class="sxs-lookup"><span data-stu-id="0dff9-105">Method</span></span>|<span data-ttu-id="0dff9-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="0dff9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0dff9-107">Método GetClass</span><span class="sxs-lookup"><span data-stu-id="0dff9-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="0dff9-108">Obtém um ponteiro de interface para o common language runtime (CLR) <xref:System.Type> do objeto que este `ICorDebugObjectValue` referências.</span><span class="sxs-lookup"><span data-stu-id="0dff9-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="0dff9-109">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="0dff9-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="0dff9-110">Não implementado.</span><span class="sxs-lookup"><span data-stu-id="0dff9-110">Not implemented.</span></span>|  
|[<span data-ttu-id="0dff9-111">Método GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="0dff9-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="0dff9-112">Obtém um ponteiro de interface para um [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) que representa o valor do campo especificado da classe especificada.</span><span class="sxs-lookup"><span data-stu-id="0dff9-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="0dff9-113">Método GetManagedCopy</span><span class="sxs-lookup"><span data-stu-id="0dff9-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="0dff9-114">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="0dff9-114">Obsolete.</span></span> <span data-ttu-id="0dff9-115">Não chame este método.</span><span class="sxs-lookup"><span data-stu-id="0dff9-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="0dff9-116">Método GetVirtualMethod</span><span class="sxs-lookup"><span data-stu-id="0dff9-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="0dff9-117">Não implementado.</span><span class="sxs-lookup"><span data-stu-id="0dff9-117">Not implemented.</span></span>|  
|[<span data-ttu-id="0dff9-118">Método IsValueClass</span><span class="sxs-lookup"><span data-stu-id="0dff9-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="0dff9-119">Obtém um valor que indica se o objeto referenciado por essa `ICorDebugObjectValue` é um tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="0dff9-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="0dff9-120">Método SetFromManagedCopy</span><span class="sxs-lookup"><span data-stu-id="0dff9-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="0dff9-121">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="0dff9-121">Obsolete.</span></span> <span data-ttu-id="0dff9-122">Não chame este método.</span><span class="sxs-lookup"><span data-stu-id="0dff9-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0dff9-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="0dff9-123">Remarks</span></span>  
 <span data-ttu-id="0dff9-124">Um `ICorDebugObjectValue` permanece válido até que o processo que está sendo depurado é continuado.</span><span class="sxs-lookup"><span data-stu-id="0dff9-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0dff9-125">Esta interface não dá suporte a que está sendo chamado remotamente, entre computadores ou entre processos.</span><span class="sxs-lookup"><span data-stu-id="0dff9-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dff9-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0dff9-126">Requirements</span></span>  
 <span data-ttu-id="0dff9-127">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dff9-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dff9-128">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0dff9-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dff9-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dff9-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dff9-130">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dff9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dff9-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0dff9-131">See Also</span></span>  
 [<span data-ttu-id="0dff9-132">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="0dff9-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 