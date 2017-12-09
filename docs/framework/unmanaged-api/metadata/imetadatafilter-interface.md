---
title: Interface IMetaDataFilter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataFilter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataFilter
helpviewer_keywords: IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7c0afbb9be9af3ffe69ddfcac85b70de53a391ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="c5b8c-102">Interface IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="c5b8c-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="c5b8c-103">Fornece métodos para a marcação e a filtragem de tokens de metadados para evitar a repetição de ações que já foi usadas.</span><span class="sxs-lookup"><span data-stu-id="c5b8c-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5b8c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c5b8c-104">Methods</span></span>  
  
|<span data-ttu-id="c5b8c-105">Método</span><span class="sxs-lookup"><span data-stu-id="c5b8c-105">Method</span></span>|<span data-ttu-id="c5b8c-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="c5b8c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c5b8c-107">Método IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="c5b8c-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="c5b8c-108">Obtém um valor que indica se o token de metadados especificado foi processado.</span><span class="sxs-lookup"><span data-stu-id="c5b8c-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="c5b8c-109">Método MarkToken</span><span class="sxs-lookup"><span data-stu-id="c5b8c-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="c5b8c-110">Define um valor que indica se o token de metadados especificado foi processado.</span><span class="sxs-lookup"><span data-stu-id="c5b8c-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="c5b8c-111">Método UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="c5b8c-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="c5b8c-112">Remove as marcas de processamento de todos os tokens no escopo atual de metadados.</span><span class="sxs-lookup"><span data-stu-id="c5b8c-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5b8c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5b8c-113">Requirements</span></span>  
 <span data-ttu-id="c5b8c-114">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5b8c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5b8c-115">**Cabeçalho:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c5b8c-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5b8c-116">**Biblioteca:** usado como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="c5b8c-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5b8c-117">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5b8c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b8c-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c5b8c-118">See Also</span></span>  
 [<span data-ttu-id="c5b8c-119">Interfaces de metadados</span><span class="sxs-lookup"><span data-stu-id="c5b8c-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)