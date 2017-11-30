---
title: "Método IHostTask::Join"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.Join
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b5dbfcfc87a520925f36e09d4f2d21dbffadfe1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="f760b-102">Método IHostTask::Join</span><span class="sxs-lookup"><span data-stu-id="f760b-102">IHostTask::Join Method</span></span>
<span data-ttu-id="f760b-103">Bloqueia a tarefa chamada até que a tarefa representada por atual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instância for concluída, o intervalo de tempo especificado expira, ou [Ihosttask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) é chamado.</span><span class="sxs-lookup"><span data-stu-id="f760b-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f760b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f760b-104">Syntax</span></span>  
  
```  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f760b-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f760b-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="f760b-106">[in] O intervalo de tempo, em milissegundos, de espera para a tarefa ser encerrada.</span><span class="sxs-lookup"><span data-stu-id="f760b-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="f760b-107">Se esse intervalo expira antes que a tarefa termina, a tarefa chamada desbloqueia.</span><span class="sxs-lookup"><span data-stu-id="f760b-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="f760b-108">[in] Uma da [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="f760b-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="f760b-109">Um valor de WAIT_ALERTABLE instrui o host para ativar a tarefa se `Alert` é chamado antes de `milliseconds` expira.</span><span class="sxs-lookup"><span data-stu-id="f760b-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f760b-110">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="f760b-110">Return Value</span></span>  
  
|<span data-ttu-id="f760b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f760b-111">HRESULT</span></span>|<span data-ttu-id="f760b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="f760b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f760b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f760b-113">S_OK</span></span>|<span data-ttu-id="f760b-114">`Join`retornou com êxito.</span><span class="sxs-lookup"><span data-stu-id="f760b-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="f760b-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f760b-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f760b-116">O common language runtime (CLR) não foi carregado em um processo ou o CLR está em um estado em que ele não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="f760b-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f760b-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f760b-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f760b-118">A chamada foi atingido.</span><span class="sxs-lookup"><span data-stu-id="f760b-118">The call timed out.</span></span>|  
|<span data-ttu-id="f760b-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f760b-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f760b-120">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="f760b-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f760b-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f760b-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f760b-122">Um evento foi cancelado durante um thread bloqueado ou fibra estava aguardando ou atual `IHostTask` instância não está associada uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="f760b-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="f760b-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f760b-123">E_FAIL</span></span>|<span data-ttu-id="f760b-124">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="f760b-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f760b-125">Quando um método retornará E_FAIL, o CLR não será mais utilizável dentro do processo.</span><span class="sxs-lookup"><span data-stu-id="f760b-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f760b-126">As chamadas subsequentes para hospedagem métodos retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f760b-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f760b-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f760b-127">Requirements</span></span>  
 <span data-ttu-id="f760b-128">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f760b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f760b-129">**Cabeçalho:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f760b-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f760b-130">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="f760b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f760b-131">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f760b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f760b-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f760b-132">See Also</span></span>  
 [<span data-ttu-id="f760b-133">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f760b-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="f760b-134">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f760b-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="f760b-135">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="f760b-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="f760b-136">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f760b-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="f760b-137">Enumeração WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="f760b-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)