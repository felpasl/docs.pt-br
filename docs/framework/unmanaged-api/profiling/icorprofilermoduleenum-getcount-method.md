---
title: "Método ICorProfilerModuleEnum::GetCount"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum.GetCount Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 930184a1d5c68ea87b2e3bc62b44a0176cd9db06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="78174-102">Método ICorProfilerModuleEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="78174-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="78174-103">Obtém o número de módulos gerenciados que foram carregados no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="78174-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78174-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="78174-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78174-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="78174-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="78174-106">[out] O número de módulos de tempo de execução na coleção.</span><span class="sxs-lookup"><span data-stu-id="78174-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78174-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78174-107">Requirements</span></span>  
 <span data-ttu-id="78174-108">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78174-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78174-109">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="78174-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="78174-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78174-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78174-111">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78174-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78174-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="78174-112">See Also</span></span>  
 [<span data-ttu-id="78174-113">Interface ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="78174-113">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="78174-114">Interfaces de criação de perfil</span><span class="sxs-lookup"><span data-stu-id="78174-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)