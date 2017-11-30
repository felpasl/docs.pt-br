---
title: "Método IGCHost::GetStats"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.GetStats
api_location: mscoree.dll
api_type: COM
f1_keywords: GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c8db4f854b73d04e7260457c978a7a644677559
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="f7e3e-102">Método IGCHost::GetStats</span><span class="sxs-lookup"><span data-stu-id="f7e3e-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="f7e3e-103">Obtém as estatísticas para o estado atual do sistema de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="f7e3e-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7e3e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f7e3e-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7e3e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f7e3e-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="f7e3e-106">[out no] Um ponteiro para um [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estrutura que contém as estatísticas para o estado atual do sistema de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="f7e3e-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7e3e-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="f7e3e-107">Remarks</span></span>  
 <span data-ttu-id="f7e3e-108">As estatísticas podem ser usadas por um sistema inteligente de alocação para operar o sistema de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="f7e3e-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="f7e3e-109">Por exemplo, o sistema de alocação pode determinar, depois de revisar as estatísticas, o que precisa adicionar mais memória ou forçar uma coleção.</span><span class="sxs-lookup"><span data-stu-id="f7e3e-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7e3e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7e3e-110">Requirements</span></span>  
 <span data-ttu-id="f7e3e-111">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7e3e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7e3e-112">**Cabeçalho:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="f7e3e-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="f7e3e-113">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="f7e3e-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7e3e-114">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7e3e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e3e-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f7e3e-115">See Also</span></span>  
 [<span data-ttu-id="f7e3e-116">Interface IGCHost</span><span class="sxs-lookup"><span data-stu-id="f7e3e-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)