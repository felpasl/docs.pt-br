---
title: Estrutura COR_NATIVE_LINK
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08d27eb834c1a9a3a5d163bb2d3054f599ae1669
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719554"
---
# <a name="cornativelink-structure"></a>Estrutura COR_NATIVE_LINK
Contém informações que são usadas para vincular o código nativo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|Descrição|  
|------------|-----------------|  
|`m_linkType`|O tipo a ser vinculado no código nativo. Esse valor é um dos [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) valores.|  
|`m_flags`|Sinalizadores usados pelo vinculador ao vincular o código nativo. Esse valor é um dos [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) valores.|  
|`m_entryPoint`|O token de metadados de MemberRef que representa o ponto de entrada. O formato é `lib:entrypoint`.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor.h  
  
 **Biblioteca:** Usado como um recurso em mscoree. dll  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também
- [Estruturas de metadados](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [Enumeração CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [Enumeração CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
