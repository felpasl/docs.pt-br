---
title: ICorDebugBreakpoint Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a222f578daed0ab81e2136e00d6f9b032acd95fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744928"
---
# <a name="icordebugbreakpoint-interface1"></a>ICorDebugBreakpoint Interface1
Representa um ponto de interrupção em uma função ou um ponto de inspeção em um valor.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descrição|  
|------------|-----------------|  
|[Método Activate](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|Define o estado ativo disso `ICorDebugBreakpoint`.|  
|[Método IsActive](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|Obtém um valor que indica se este `ICorDebugBreakpoint` está ativa.|  
  
## <a name="remarks"></a>Comentários  
 Pontos de interrupção não suportam diretamente expressões condicionais. Se desejar essa funcionalidade, um depurador deve implementar a ele na parte superior da `ICorDebugBreakpoint`.  
  
 Estende a interface ICorDebugFunctionBreakpoint `ICorDebugBreakpoint` para dar suporte a pontos de interrupção em funções.  
  
> [!NOTE]
>  Essa interface não dá suporte a ser chamada remotamente, entre computadores ou entre processos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também
- [Depurando interfaces](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
